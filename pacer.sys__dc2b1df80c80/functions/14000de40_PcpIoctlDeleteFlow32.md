# PcpIoctlDeleteFlow32

- ea: `0x14000de40`
- end: `0x14000df90`
- name: `PcpIoctlDeleteFlow32`
- size: `336`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140020b50`

## callees

- `0x140003934`
- `0x140005578`
- `0x14000db88`
- `0x14000de40`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14000dee0`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000df12`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000df54`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000dee0`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000df12`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000df54`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000deb5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000deb5`

## pseudocode

```c
__int64 __fastcall PcpIoctlDeleteFlow32(__int64 a1, __int64 a2, _DWORD *a3)
{
  bool v3; // cf
  __int64 result; // rax
  int *v6; // rdi
  int FlowByHandle32; // ebx
  __int64 v8; // rbx
  KSPIN_LOCK *v9; // r14
  KIRQL v10; // r15
  char *v11; // rsi
  char **v12; // rcx
  PVOID *v13; // rdx
  __int64 v14; // rdx
  PVOID P; // [rsp+50h] [rbp+8h] BYREF

  v3 = *(_DWORD *)(a2 + 8) < 0xCu;
  P = 0;
  if ( v3 )
    return 3221225507LL;
  v6 = *(int **)(a1 + 24);
  if ( *(_DWORD *)(a2 + 16) >= 8u )
  {
    if ( v6[1] )
    {
      v8 = *(_QWORD *)(*(_QWORD *)(a2 + 48) + 24LL);
      v9 = (KSPIN_LOCK *)(v8 + 32);
      v10 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v8 + 32));
      FlowByHandle32 = PcpFindFlowByHandle32((unsigned int)v6[1], v8, &P);
      if ( FlowByHandle32 >= 0 )
      {
        v11 = (char *)P;
        RtlAcquireReadLockAtDpcLevel((PKSPIN_LOCK)P + 12);
        if ( *((char **)v11 + 71) == v11 + 568 )
        {
          v12 = (char **)*((_QWORD *)v11 + 2);
          if ( v12[1] != v11 + 16 || (v13 = (PVOID *)*((_QWORD *)v11 + 3), *v13 != v11 + 16) )
            __fastfail(3u);
          *v13 = v12;
          v12[1] = (char *)v13;
          _InterlockedDecrement((volatile signed __int32 *)v11 + 26);
          KeReleaseSpinLock(v9, v10);
          v6[2] = *((_DWORD *)v11 + 148);
          v6[1] = 0;
          PcpDeleteFlow(v11, v14);
          goto LABEL_15;
        }
        _InterlockedDecrement((volatile signed __int32 *)v11 + 26);
        KeReleaseSpinLock(v9, v10);
        FlowByHandle32 = -1073741567;
      }
      else
      {
        KeReleaseSpinLock(v9, v10);
      }
    }
    else
    {
      FlowByHandle32 = -1073741275;
    }
  }
  else
  {
    FlowByHandle32 = -1073741789;
  }
  *(_QWORD *)(v6 + 1) = 0;
LABEL_15:
  *v6 = FlowByHandle32;
  result = (unsigned int)FlowByHandle32;
  *a3 = 12;
  return result;
}

```

## disassembly

```asm
0x14000de40  mov     [rsp+arg_8], rbx
0x14000de45  mov     [rsp+arg_10], rbp
0x14000de4a  push    rsi
0x14000de4b  push    rdi
0x14000de4c  push    r12
0x14000de4e  push    r14
0x14000de50  push    r15
0x14000de52  sub     rsp, 20h
0x14000de56  cmp     dword ptr [rdx+8], 0Ch
0x14000de5a  mov     r12, r8
0x14000de5d  mov     [rsp+48h+P], 0
0x14000de66  jnb     short loc_14000DE85
0x14000de68  mov     eax, 0C0000023h
0x14000de6d  mov     rbx, [rsp+48h+arg_8]
0x14000de72  mov     rbp, [rsp+48h+arg_10]
0x14000de77  add     rsp, 20h
0x14000de7b  pop     r15
0x14000de7d  pop     r14
0x14000de7f  pop     r12
0x14000de81  pop     rdi
0x14000de82  pop     rsi
0x14000de83  retn
0x14000de85  cmp     dword ptr [rdx+10h], 8
0x14000de89  mov     rdi, [rcx+18h]
0x14000de8d  jnb     short loc_14000DE99
0x14000de8f  mov     ebx, 0C0000023h
0x14000de94  jmp     loc_14000DF23
0x14000de99  cmp     dword ptr [rdi+4], 0
0x14000de9d  jnz     short loc_14000DEA6
0x14000de9f  mov     ebx, 0C0000225h
0x14000dea4  jmp     short loc_14000DF23
0x14000dea6  mov     rax, [rdx+30h]
0x14000deaa  mov     rbx, [rax+18h]
0x14000deae  lea     r14, [rbx+20h]
0x14000deb2  mov     rcx, r14; SpinLock
0x14000deb5  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000debc  nop     dword ptr [rax+rax+00h]
0x14000dec1  mov     ecx, [rdi+4]
0x14000dec4  lea     r8, [rsp+48h+P]
0x14000dec9  mov     rdx, rbx
0x14000decc  mov     r15b, al
0x14000decf  call    PcpFindFlowByHandle32
0x14000ded4  mov     ebx, eax
0x14000ded6  test    eax, eax
0x14000ded8  jns     short loc_14000DEEE
0x14000deda  mov     dl, r15b; NewIrql
0x14000dedd  mov     rcx, r14; SpinLock
0x14000dee0  call    cs:__imp_KeReleaseSpinLock
0x14000dee7  nop     dword ptr [rax+rax+00h]
0x14000deec  jmp     short loc_14000DF23
0x14000deee  mov     rsi, [rsp+48h+P]
0x14000def3  lea     rcx, [rsi+60h]; SpinLock
0x14000def7  call    RtlAcquireReadLockAtDpcLevel
0x14000defc  lea     rax, [rsi+238h]
0x14000df03  cmp     [rax], rax
0x14000df06  jz      short loc_14000DF2D
0x14000df08  lock dec dword ptr [rsi+68h]
0x14000df0c  mov     dl, r15b; NewIrql
0x14000df0f  mov     rcx, r14; SpinLock
0x14000df12  call    cs:__imp_KeReleaseSpinLock
0x14000df19  nop     dword ptr [rax+rax+00h]
0x14000df1e  mov     ebx, 0C0000101h
0x14000df23  mov     qword ptr [rdi+4], 0
0x14000df2b  jmp     short loc_14000DF78
0x14000df2d  lea     rax, [rsi+10h]
0x14000df31  mov     rcx, [rax]
0x14000df34  cmp     [rcx+8], rax
0x14000df38  jnz     short loc_14000DF89
0x14000df3a  mov     rdx, [rax+8]
0x14000df3e  cmp     [rdx], rax
0x14000df41  jnz     short loc_14000DF89
0x14000df43  mov     [rdx], rcx
0x14000df46  mov     [rcx+8], rdx
0x14000df4a  mov     dl, r15b; NewIrql
0x14000df4d  lock dec dword ptr [rsi+68h]
0x14000df51  mov     rcx, r14; SpinLock
0x14000df54  call    cs:__imp_KeReleaseSpinLock
0x14000df5b  nop     dword ptr [rax+rax+00h]
0x14000df60  mov     eax, [rsi+250h]
0x14000df66  mov     rcx, rsi; P
0x14000df69  mov     [rdi+8], eax
0x14000df6c  mov     dword ptr [rdi+4], 0
0x14000df73  call    PcpDeleteFlow
0x14000df78  mov     [rdi], ebx
0x14000df7a  mov     eax, ebx
0x14000df7c  mov     dword ptr [r12], 0Ch
0x14000df84  jmp     loc_14000DE6D
0x14000df89  mov     ecx, 3
0x14000df8e  int     29h; Win8: RtlFailFast(ecx)
```
