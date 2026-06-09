# VidSchiProcessAsyncLiveDump

- ea: `0x14004f3c0`
- end: `0x14004f606`
- name: `VidSchiProcessAsyncLiveDump`
- size: `582`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation`

## callees

- `0x140021c90`
- `0x14002a250`
- `0x14004f3c0`
- `0x140058680`
- `0x140058ac0`

## import_xrefs

- `ntoskrnl!ExFreeToLookasideListEx` at `0x14004f566`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14004f566`
- `ntoskrnl!KeSetEvent` at `0x14004f456`
- `ntoskrnl!KeSetEvent` at `0x14004f456`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004f5d9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004f5d9`
- `ntoskrnl!ExAllocatePool2` at `0x14004f4bd`
- `ntoskrnl!ExAllocatePool2` at `0x14004f4bd`
- `watchdog!WdLogSingleEntry1` at `0x14004f48f`
- `watchdog!WdLogSingleEntry1` at `0x14004f48f`
- `dxgkrnl!DxgCreateLiveDumpWithWdLogs` at `0x14004f5aa`
- `dxgkrnl!DxgCreateLiveDumpWithWdLogs` at `0x14004f5aa`

## pseudocode

```c
void __fastcall VidSchiProcessAsyncLiveDump(__int64 a1)
{
  unsigned __int64 v2; // rdi
  _BYTE *Pool2; // rbx
  _BYTE *v4; // r15
  unsigned int v5; // esi
  __int64 v6; // rbx
  __int64 v7; // r12
  _QWORD *v8; // rsi
  _QWORD *v9; // rax
  _QWORD *v10; // rcx
  _OWORD *v11; // rdx
  __int64 v12; // rcx
  int v13; // [rsp+28h] [rbp-D8h]
  _BYTE v14[48]; // [rsp+30h] [rbp-D0h] BYREF
  PVOID P; // [rsp+60h] [rbp-A0h]
  _BYTE v16[120]; // [rsp+68h] [rbp-98h] BYREF
  int v17; // [rsp+E0h] [rbp-20h]

  P = 0;
  v17 = 0;
  AcquireSpinLock::AcquireSpinLock((AcquireSpinLock *)v14, (unsigned __int64 *)(a1 + 7736), 1, 0);
  AcquireSpinLock::Release((AcquireSpinLock *)v14);
  v2 = *(unsigned int *)(a1 + 7792);
  if ( (unsigned int)v2 <= 3 )
  {
    Pool2 = v16;
    P = v16;
    if ( (_DWORD)v2 )
    {
      memset(v16, 0, 40 * v2);
      Pool2 = P;
    }
  }
  else
  {
    if ( 0xFFFFFFFFFFFFFFFFuLL / v2 < 0x28 )
    {
      Pool2 = 0;
      v4 = 0;
      goto LABEL_4;
    }
    Pool2 = (_BYTE *)ExAllocatePool2(64, 40 * v2, 895641942);
    P = Pool2;
  }
  v17 = v2;
  v4 = Pool2;
  if ( Pool2 )
  {
    v7 = 0;
    v8 = *(_QWORD **)(a1 + 7776);
    if ( v8 != (_QWORD *)(a1 + 7776) )
    {
      while ( 1 )
      {
        v9 = (_QWORD *)*v8;
        if ( *(_QWORD **)(*v8 + 8LL) != v8 || (v10 = (_QWORD *)v8[1], (_QWORD *)*v10 != v8) )
          __fastfail(3u);
        *v10 = v9;
        v11 = v8 - 1;
        v9[1] = v10;
        v8 = v9;
        v12 = 5 * v7;
        *(_OWORD *)&Pool2[8 * v12] = *v11;
        *(_OWORD *)&Pool2[8 * v12 + 16] = v11[1];
        *(_QWORD *)&Pool2[8 * v12 + 32] = *((_QWORD *)v11 + 4);
        ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(a1 + 7808), v11);
        if ( v8 == (_QWORD *)(a1 + 7776) )
          break;
        v7 = (unsigned int)(v7 + 1);
      }
    }
  }
LABEL_4:
  *(_DWORD *)(a1 + 7792) = 0;
  KeSetEvent((PRKEVENT)(a1 + 7904), 0, 0);
  if ( Pool2 )
  {
    v5 = 0;
    if ( (_DWORD)v2 )
    {
      v6 = 0;
      do
      {
        if ( *(_DWORD *)&v4[40 * v6] )
        {
          WdLogSingleEntry1(3, *(int *)&v4[40 * v6]);
          WdLogGlobalForLineNumber = 31626;
        }
        else
        {
          LOBYTE(v13) = 1;
          DxgCreateLiveDumpWithWdLogs(
            403,
            2079,
            *(unsigned int *)&v4[40 * v6 + 24],
            *(unsigned int *)&v4[40 * v6 + 28],
            *(unsigned int *)&v4[40 * v6 + 32],
            v13);
        }
        ++v5;
        ++v6;
      }
      while ( v5 < (unsigned int)v2 );
    }
  }
  if ( P != v16 )
  {
    if ( P )
      ExFreePoolWithTag(P, 0);
  }
}

```

## disassembly

```asm
0x14004f3c0  push    rbp
0x14004f3c2  push    rbx
0x14004f3c3  push    rsi
0x14004f3c4  push    rdi
0x14004f3c5  push    r12
0x14004f3c7  push    r13
0x14004f3c9  push    r14
0x14004f3cb  push    r15
0x14004f3cd  lea     rbp, [rsp-8]
0x14004f3d2  sub     rsp, 108h
0x14004f3d9  mov     rax, cs:__security_cookie
0x14004f3e0  xor     rax, rsp
0x14004f3e3  mov     [rbp+40h+var_50], rax
0x14004f3e7  mov     r14, rcx
0x14004f3ea  mov     [rsp+140h+P], 0
0x14004f3f3  lea     rdx, [rcx+1E38h]; unsigned __int64 *
0x14004f3fa  mov     [rbp+40h+var_60], 0
0x14004f401  lea     rcx, [rsp+140h+var_110]; this
0x14004f406  xor     r9d, r9d; bool
0x14004f409  mov     r8b, 1; bool
0x14004f40c  call    ??0AcquireSpinLock@@QEAA@AEA_K_N1@Z; AcquireSpinLock::AcquireSpinLock(unsigned __int64 &,bool,bool)
0x14004f411  lea     rcx, [rsp+140h+var_110]; this
0x14004f416  call    ?Release@AcquireSpinLock@@QEAAXXZ; AcquireSpinLock::Release(void)
0x14004f41b  mov     edi, [r14+1E70h]
0x14004f422  cmp     edi, 3
0x14004f425  jbe     loc_14004F4D3
0x14004f42b  xor     edx, edx
0x14004f42d  or      rax, 0FFFFFFFFFFFFFFFFh
0x14004f431  div     rdi
0x14004f434  cmp     rax, 28h ; '('
0x14004f438  jnb     short loc_14004F4AA
0x14004f43a  xor     ebx, ebx
0x14004f43c  xor     r15d, r15d
0x14004f43f  lea     rcx, [r14+1EE0h]; Event
0x14004f446  mov     dword ptr [r14+1E70h], 0
0x14004f451  xor     r8d, r8d; Wait
0x14004f454  xor     edx, edx; Increment
0x14004f456  call    cs:__imp_KeSetEvent
0x14004f45d  nop     dword ptr [rax+rax+00h]
0x14004f462  test    rbx, rbx
0x14004f465  jz      loc_14004F5C3
0x14004f46b  xor     esi, esi
0x14004f46d  test    edi, edi
0x14004f46f  jz      loc_14004F5C3
0x14004f475  xor     ebx, ebx
0x14004f477  lea     rcx, [rbx+rbx*4]
0x14004f47b  movsxd  rax, dword ptr [r15+rcx*8]
0x14004f47f  test    eax, eax
0x14004f481  jz      loc_14004F587
0x14004f487  mov     rdx, rax
0x14004f48a  mov     ecx, 3
0x14004f48f  call    cs:__imp_WdLogSingleEntry1
0x14004f496  nop     dword ptr [rax+rax+00h]
0x14004f49b  mov     cs:WdLogGlobalForLineNumber, 7B8Ah
0x14004f4a5  jmp     loc_14004F5B6
0x14004f4aa  lea     rdx, [rdi+rdi*4]
0x14004f4ae  mov     ecx, 40h ; '@'
0x14004f4b3  shl     rdx, 3
0x14004f4b7  mov     r8d, 35626956h
0x14004f4bd  call    cs:__imp_ExAllocatePool2
0x14004f4c4  nop     dword ptr [rax+rax+00h]
0x14004f4c9  mov     rbx, rax
0x14004f4cc  mov     [rsp+140h+P], rax
0x14004f4d1  jmp     short loc_14004F4FA
0x14004f4d3  lea     rbx, [rsp+140h+var_D8]
0x14004f4d8  mov     [rsp+140h+P], rbx
0x14004f4dd  test    edi, edi
0x14004f4df  jz      short loc_14004F4FA
0x14004f4e1  lea     r8, [rdi+rdi*4]
0x14004f4e5  xor     edx, edx; Val
0x14004f4e7  shl     r8, 3; Size
0x14004f4eb  lea     rcx, [rsp+140h+var_D8]; void *
0x14004f4f0  call    memset
0x14004f4f5  mov     rbx, [rsp+140h+P]
0x14004f4fa  mov     [rbp+40h+var_60], edi
0x14004f4fd  mov     r15, rbx
0x14004f500  test    rbx, rbx
0x14004f503  jz      loc_14004F43F
0x14004f509  lea     r13, [r14+1E60h]
0x14004f510  xor     r12d, r12d
0x14004f513  mov     rsi, [r13+0]
0x14004f517  cmp     rsi, r13
0x14004f51a  jz      loc_14004F43F
0x14004f520  mov     rax, [rsi]
0x14004f523  cmp     [rax+8], rsi
0x14004f527  jnz     short loc_14004F580
0x14004f529  mov     rcx, [rsi+8]
0x14004f52d  cmp     [rcx], rsi
0x14004f530  jnz     short loc_14004F580
0x14004f532  mov     [rcx], rax
0x14004f535  lea     rdx, [rsi-8]; Entry
0x14004f539  mov     [rax+8], rcx
0x14004f53d  mov     rsi, rax
0x14004f540  movups  xmm0, xmmword ptr [rdx]
0x14004f543  lea     rcx, [r12+r12*4]
0x14004f547  movups  xmmword ptr [rbx+rcx*8], xmm0
0x14004f54b  movups  xmm1, xmmword ptr [rdx+10h]
0x14004f54f  movups  xmmword ptr [rbx+rcx*8+10h], xmm1
0x14004f554  movsd   xmm0, qword ptr [rdx+20h]
0x14004f559  movsd   qword ptr [rbx+rcx*8+20h], xmm0
0x14004f55f  lea     rcx, [r14+1E80h]; Lookaside
0x14004f566  call    cs:__imp_ExFreeToLookasideListEx
0x14004f56d  nop     dword ptr [rax+rax+00h]
0x14004f572  cmp     rsi, r13
0x14004f575  jz      loc_14004F43F
0x14004f57b  inc     r12d
0x14004f57e  jmp     short loc_14004F520
0x14004f580  mov     ecx, 3
0x14004f585  int     29h; Win8: RtlFailFast(ecx)
0x14004f587  mov     eax, [r15+rcx*8+20h]
0x14004f58c  mov     edx, 81Fh
0x14004f591  mov     r9d, [r15+rcx*8+1Ch]
0x14004f596  mov     r8d, [r15+rcx*8+18h]
0x14004f59b  mov     ecx, 193h
0x14004f5a0  mov     [rsp+140h+var_118], 1
0x14004f5a5  mov     [rsp+140h+var_120], rax
0x14004f5aa  call    cs:__imp_?DxgCreateLiveDumpWithWdLogs@@YAJK_K000T_WD_LIVEREPORT_FLAGS@@@Z; DxgCreateLiveDumpWithWdLogs(ulong,unsigned __int64,unsigned __int64,unsigned __int64,unsigned __int64,_WD_LIVEREPORT_FLAGS)
0x14004f5b1  nop     dword ptr [rax+rax+00h]
0x14004f5b6  inc     esi
0x14004f5b8  inc     rbx
0x14004f5bb  cmp     esi, edi
0x14004f5bd  jb      loc_14004F477
0x14004f5c3  mov     rcx, [rsp+140h+P]; P
0x14004f5c8  lea     rax, [rsp+140h+var_D8]
0x14004f5cd  cmp     rcx, rax
0x14004f5d0  jz      short loc_14004F5E5
0x14004f5d2  test    rcx, rcx
0x14004f5d5  jz      short loc_14004F5E5
0x14004f5d7  xor     edx, edx; Tag
0x14004f5d9  call    cs:__imp_ExFreePoolWithTag
0x14004f5e0  nop     dword ptr [rax+rax+00h]
0x14004f5e5  mov     rcx, [rbp+40h+var_50]
0x14004f5e9  xor     rcx, rsp; StackCookie
0x14004f5ec  call    __security_check_cookie
0x14004f5f1  add     rsp, 108h
0x14004f5f8  pop     r15
0x14004f5fa  pop     r14
0x14004f5fc  pop     r13
0x14004f5fe  pop     r12
0x14004f600  pop     rdi
0x14004f601  pop     rsi
0x14004f602  pop     rbx
0x14004f603  pop     rbp
0x14004f604  retn
```
