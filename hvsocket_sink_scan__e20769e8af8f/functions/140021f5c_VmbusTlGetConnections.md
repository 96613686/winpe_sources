# VmbusTlGetConnections

- ea: `0x140021f5c`
- end: `0x14002209f`
- name: `VmbusTlGetConnections`
- size: `323`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, service_task`

## callers

- `0x14001a790`

## callees

- `0x14000a154`
- `0x140021f5c`

## import_xrefs

- `ntoskrnl!PsGetProcessId` at `0x140021feb`
- `ntoskrnl!PsGetProcessId` at `0x140021feb`

## pseudocode

```c
__int64 __fastcall VmbusTlGetConnections(__int64 a1, unsigned int a2, __int64 a3, unsigned int *a4)
{
  _QWORD *v4; // r13
  _QWORD *v5; // rdi
  unsigned int v6; // esi
  unsigned int v8; // ebp
  __int64 *i; // rbx
  __int64 v10; // r15
  int v11; // eax

  v4 = (_QWORD *)(a1 + 360);
  v5 = *(_QWORD **)(a1 + 360);
  v6 = 0;
  v8 = a2 / 0x38;
LABEL_12:
  if ( v5 == v4 )
  {
    *a4 = v6;
    return 0;
  }
  else
  {
    for ( i = (__int64 *)v5[27]; ; i = (__int64 *)*i )
    {
      if ( i == v5 + 27 )
      {
        v5 = (_QWORD *)*v5;
        goto LABEL_12;
      }
      if ( v6 == v8 )
        break;
      if ( (*((_DWORD *)i + 99) & 0x40) != 0 )
      {
        v10 = 56LL * v6;
        *(_OWORD *)(v10 + a3) = *(_OWORD *)((char *)i + 36);
        *(_OWORD *)(v10 + a3 + 16) = *(_OWORD *)((char *)i + 20);
        *(_DWORD *)(v10 + a3 + 32) = (unsigned int)PsGetProcessId((PEPROCESS)i[19]);
        *(_QWORD *)(v10 + a3 + 40) = i[24];
        if ( (i[51] & 3) != 0 || (v11 = 1, *((_DWORD *)i + 100)) )
          v11 = 2;
        *(_DWORD *)(v10 + a3 + 48) = v11;
        ++v6;
      }
    }
    if ( (unsigned int)dword_140013058 > 2 )
      HvsocketTraceServiceError((unsigned int)"VmbusTlGetConnections", 764, -1073741789, (_DWORD)v5 + 16, a1 + 232);
    return 3221225507LL;
  }
}

```

## disassembly

```asm
0x140021f5c  mov     [rsp+arg_8], rbx
0x140021f61  mov     [rsp+arg_18], r9
0x140021f66  mov     [rsp+arg_0], rcx
0x140021f6b  push    rbp
0x140021f6c  push    rsi
0x140021f6d  push    rdi
0x140021f6e  push    r12
0x140021f70  push    r13
0x140021f72  push    r14
0x140021f74  push    r15
0x140021f76  sub     rsp, 30h
0x140021f7a  mov     ebp, edx
0x140021f7c  lea     r13, [rcx+168h]
0x140021f83  mov     rdi, [r13+0]
0x140021f87  mov     rax, 2492492492492493h
0x140021f91  mul     rbp
0x140021f94  xor     esi, esi
0x140021f96  mov     r12, r8
0x140021f99  sub     rbp, rdx
0x140021f9c  shr     rbp, 1
0x140021f9f  add     rbp, rdx
0x140021fa2  shr     rbp, 5
0x140021fa6  jmp     loc_140022037
0x140021fab  lea     r14, [rdi+0D8h]
0x140021fb2  mov     rbx, [r14]
0x140021fb5  jmp     short loc_14002202F
0x140021fb7  cmp     esi, ebp
0x140021fb9  jz      loc_140022062
0x140021fbf  mov     eax, [rbx+18Ch]
0x140021fc5  test    al, 40h
0x140021fc7  jz      short loc_14002202C
0x140021fc9  movups  xmm0, xmmword ptr [rbx+24h]
0x140021fcd  mov     eax, esi
0x140021fcf  imul    r15, rax, 38h ; '8'
0x140021fd3  movdqu  xmmword ptr [r15+r12], xmm0
0x140021fd9  movups  xmm1, xmmword ptr [rbx+14h]
0x140021fdd  movdqu  xmmword ptr [r15+r12+10h], xmm1
0x140021fe4  mov     rcx, [rbx+98h]; Process
0x140021feb  call    cs:__imp_PsGetProcessId
0x140021ff2  nop     dword ptr [rax+rax+00h]
0x140021ff7  mov     [r15+r12+20h], eax
0x140021ffc  mov     rax, [rbx+0C0h]
0x140022003  mov     [r15+r12+28h], rax
0x140022008  mov     eax, [rbx+198h]
0x14002200e  test    al, 3
0x140022010  jnz     short loc_140022020
0x140022012  cmp     dword ptr [rbx+190h], 0
0x140022019  mov     eax, 1
0x14002201e  jz      short loc_140022025
0x140022020  mov     eax, 2
0x140022025  mov     [r15+r12+30h], eax
0x14002202a  inc     esi
0x14002202c  mov     rbx, [rbx]
0x14002202f  cmp     rbx, r14
0x140022032  jnz     short loc_140021FB7
0x140022034  mov     rdi, [rdi]
0x140022037  cmp     rdi, r13
0x14002203a  jnz     loc_140021FAB
0x140022040  mov     rax, [rsp+68h+arg_18]
0x140022048  mov     [rax], esi
0x14002204a  xor     eax, eax
0x14002204c  mov     rbx, [rsp+68h+arg_8]
0x140022051  add     rsp, 30h
0x140022055  pop     r15
0x140022057  pop     r14
0x140022059  pop     r13
0x14002205b  pop     r12
0x14002205d  pop     rdi
0x14002205e  pop     rsi
0x14002205f  pop     rbp
0x140022060  retn
0x140022062  mov     ecx, cs:dword_140013058
0x140022068  mov     ebx, 0C0000023h
0x14002206d  cmp     ecx, 2
0x140022070  jbe     short loc_14002209B
0x140022072  mov     rcx, [rsp+68h+arg_0]
0x140022077  lea     r9, [rdi+10h]
0x14002207b  add     rcx, 0E8h
0x140022082  mov     r8d, ebx
0x140022085  mov     [rsp+68h+var_48], rcx
0x14002208a  mov     edx, 2FCh
0x14002208f  lea     rcx, aVmbustlgetconn; "VmbusTlGetConnections"
0x140022096  call    HvsocketTraceServiceError
0x14002209b  mov     eax, ebx
0x14002209d  jmp     short loc_14002204C
```
