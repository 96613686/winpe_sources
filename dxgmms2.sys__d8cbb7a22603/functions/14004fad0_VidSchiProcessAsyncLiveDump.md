# VidSchiProcessAsyncLiveDump

- ea: `0x14004fad0`
- end: `0x14004fd16`
- name: `VidSchiProcessAsyncLiveDump`
- size: `582`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation`

## callees

- `0x14001f640`
- `0x140027b90`
- `0x14004fad0`
- `0x140058f50`
- `0x140059380`

## import_xrefs

- `ntoskrnl!ExFreeToLookasideListEx` at `0x14004fc76`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14004fc76`
- `ntoskrnl!KeSetEvent` at `0x14004fb66`
- `ntoskrnl!KeSetEvent` at `0x14004fb66`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004fce9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004fce9`
- `ntoskrnl!ExAllocatePool2` at `0x14004fbcd`
- `ntoskrnl!ExAllocatePool2` at `0x14004fbcd`
- `watchdog!WdLogSingleEntry1` at `0x14004fb9f`
- `watchdog!WdLogSingleEntry1` at `0x14004fb9f`
- `dxgkrnl!DxgCreateLiveDumpWithWdLogs` at `0x14004fcba`
- `dxgkrnl!DxgCreateLiveDumpWithWdLogs` at `0x14004fcba`

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
          WdLogGlobalForLineNumber = 31687;
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
0x14004fad0  push    rbp
0x14004fad2  push    rbx
0x14004fad3  push    rsi
0x14004fad4  push    rdi
0x14004fad5  push    r12
0x14004fad7  push    r13
0x14004fad9  push    r14
0x14004fadb  push    r15
0x14004fadd  lea     rbp, [rsp-8]
0x14004fae2  sub     rsp, 108h
0x14004fae9  mov     rax, cs:__security_cookie
0x14004faf0  xor     rax, rsp
0x14004faf3  mov     [rbp+40h+var_50], rax
0x14004faf7  mov     r14, rcx
0x14004fafa  mov     [rsp+140h+P], 0
0x14004fb03  lea     rdx, [rcx+1E38h]; unsigned __int64 *
0x14004fb0a  mov     [rbp+40h+var_60], 0
0x14004fb11  lea     rcx, [rsp+140h+var_110]; this
0x14004fb16  xor     r9d, r9d; bool
0x14004fb19  mov     r8b, 1; bool
0x14004fb1c  call    ??0AcquireSpinLock@@QEAA@AEA_K_N1@Z; AcquireSpinLock::AcquireSpinLock(unsigned __int64 &,bool,bool)
0x14004fb21  lea     rcx, [rsp+140h+var_110]; this
0x14004fb26  call    ?Release@AcquireSpinLock@@QEAAXXZ; AcquireSpinLock::Release(void)
0x14004fb2b  mov     edi, [r14+1E70h]
0x14004fb32  cmp     edi, 3
0x14004fb35  jbe     loc_14004FBE3
0x14004fb3b  xor     edx, edx
0x14004fb3d  or      rax, 0FFFFFFFFFFFFFFFFh
0x14004fb41  div     rdi
0x14004fb44  cmp     rax, 28h ; '('
0x14004fb48  jnb     short loc_14004FBBA
0x14004fb4a  xor     ebx, ebx
0x14004fb4c  xor     r15d, r15d
0x14004fb4f  lea     rcx, [r14+1EE0h]; Event
0x14004fb56  mov     dword ptr [r14+1E70h], 0
0x14004fb61  xor     r8d, r8d; Wait
0x14004fb64  xor     edx, edx; Increment
0x14004fb66  call    cs:__imp_KeSetEvent
0x14004fb6d  nop     dword ptr [rax+rax+00h]
0x14004fb72  test    rbx, rbx
0x14004fb75  jz      loc_14004FCD3
0x14004fb7b  xor     esi, esi
0x14004fb7d  test    edi, edi
0x14004fb7f  jz      loc_14004FCD3
0x14004fb85  xor     ebx, ebx
0x14004fb87  lea     rcx, [rbx+rbx*4]
0x14004fb8b  movsxd  rax, dword ptr [r15+rcx*8]
0x14004fb8f  test    eax, eax
0x14004fb91  jz      loc_14004FC97
0x14004fb97  mov     rdx, rax
0x14004fb9a  mov     ecx, 3
0x14004fb9f  call    cs:__imp_WdLogSingleEntry1
0x14004fba6  nop     dword ptr [rax+rax+00h]
0x14004fbab  mov     cs:WdLogGlobalForLineNumber, 7BC7h
0x14004fbb5  jmp     loc_14004FCC6
0x14004fbba  lea     rdx, [rdi+rdi*4]
0x14004fbbe  mov     ecx, 40h ; '@'
0x14004fbc3  shl     rdx, 3
0x14004fbc7  mov     r8d, 35626956h
0x14004fbcd  call    cs:__imp_ExAllocatePool2
0x14004fbd4  nop     dword ptr [rax+rax+00h]
0x14004fbd9  mov     rbx, rax
0x14004fbdc  mov     [rsp+140h+P], rax
0x14004fbe1  jmp     short loc_14004FC0A
0x14004fbe3  lea     rbx, [rsp+140h+var_D8]
0x14004fbe8  mov     [rsp+140h+P], rbx
0x14004fbed  test    edi, edi
0x14004fbef  jz      short loc_14004FC0A
0x14004fbf1  lea     r8, [rdi+rdi*4]
0x14004fbf5  xor     edx, edx; Val
0x14004fbf7  shl     r8, 3; Size
0x14004fbfb  lea     rcx, [rsp+140h+var_D8]; void *
0x14004fc00  call    memset
0x14004fc05  mov     rbx, [rsp+140h+P]
0x14004fc0a  mov     [rbp+40h+var_60], edi
0x14004fc0d  mov     r15, rbx
0x14004fc10  test    rbx, rbx
0x14004fc13  jz      loc_14004FB4F
0x14004fc19  lea     r13, [r14+1E60h]
0x14004fc20  xor     r12d, r12d
0x14004fc23  mov     rsi, [r13+0]
0x14004fc27  cmp     rsi, r13
0x14004fc2a  jz      loc_14004FB4F
0x14004fc30  mov     rax, [rsi]
0x14004fc33  cmp     [rax+8], rsi
0x14004fc37  jnz     short loc_14004FC90
0x14004fc39  mov     rcx, [rsi+8]
0x14004fc3d  cmp     [rcx], rsi
0x14004fc40  jnz     short loc_14004FC90
0x14004fc42  mov     [rcx], rax
0x14004fc45  lea     rdx, [rsi-8]; Entry
0x14004fc49  mov     [rax+8], rcx
0x14004fc4d  mov     rsi, rax
0x14004fc50  movups  xmm0, xmmword ptr [rdx]
0x14004fc53  lea     rcx, [r12+r12*4]
0x14004fc57  movups  xmmword ptr [rbx+rcx*8], xmm0
0x14004fc5b  movups  xmm1, xmmword ptr [rdx+10h]
0x14004fc5f  movups  xmmword ptr [rbx+rcx*8+10h], xmm1
0x14004fc64  movsd   xmm0, qword ptr [rdx+20h]
0x14004fc69  movsd   qword ptr [rbx+rcx*8+20h], xmm0
0x14004fc6f  lea     rcx, [r14+1E80h]; Lookaside
0x14004fc76  call    cs:__imp_ExFreeToLookasideListEx
0x14004fc7d  nop     dword ptr [rax+rax+00h]
0x14004fc82  cmp     rsi, r13
0x14004fc85  jz      loc_14004FB4F
0x14004fc8b  inc     r12d
0x14004fc8e  jmp     short loc_14004FC30
0x14004fc90  mov     ecx, 3
0x14004fc95  int     29h; Win8: RtlFailFast(ecx)
0x14004fc97  mov     eax, [r15+rcx*8+20h]
0x14004fc9c  mov     edx, 81Fh
0x14004fca1  mov     r9d, [r15+rcx*8+1Ch]
0x14004fca6  mov     r8d, [r15+rcx*8+18h]
0x14004fcab  mov     ecx, 193h
0x14004fcb0  mov     [rsp+140h+var_118], 1
0x14004fcb5  mov     [rsp+140h+var_120], rax
0x14004fcba  call    cs:__imp_?DxgCreateLiveDumpWithWdLogs@@YAJK_K000T_WD_LIVEREPORT_FLAGS@@@Z; DxgCreateLiveDumpWithWdLogs(ulong,unsigned __int64,unsigned __int64,unsigned __int64,unsigned __int64,_WD_LIVEREPORT_FLAGS)
0x14004fcc1  nop     dword ptr [rax+rax+00h]
0x14004fcc6  inc     esi
0x14004fcc8  inc     rbx
0x14004fccb  cmp     esi, edi
0x14004fccd  jb      loc_14004FB87
0x14004fcd3  mov     rcx, [rsp+140h+P]; P
0x14004fcd8  lea     rax, [rsp+140h+var_D8]
0x14004fcdd  cmp     rcx, rax
0x14004fce0  jz      short loc_14004FCF5
0x14004fce2  test    rcx, rcx
0x14004fce5  jz      short loc_14004FCF5
0x14004fce7  xor     edx, edx; Tag
0x14004fce9  call    cs:__imp_ExFreePoolWithTag
0x14004fcf0  nop     dword ptr [rax+rax+00h]
0x14004fcf5  mov     rcx, [rbp+40h+var_50]
0x14004fcf9  xor     rcx, rsp; StackCookie
0x14004fcfc  call    __security_check_cookie
0x14004fd01  add     rsp, 108h
0x14004fd08  pop     r15
0x14004fd0a  pop     r14
0x14004fd0c  pop     r13
0x14004fd0e  pop     r12
0x14004fd10  pop     rdi
0x14004fd11  pop     rsi
0x14004fd12  pop     rbx
0x14004fd13  pop     rbp
0x14004fd14  retn
```
