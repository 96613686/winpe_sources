# HacpRemoveEntry

- ea: `0x1400206e4`
- end: `0x14002087b`
- name: `HacpRemoveEntry`
- size: `407`
- prototype: ``
- caller_count: `6`
- callee_count: `5`
- tags: ``

## callers

- `0x140003bd0`
- `0x140005c90`
- `0x14000c370`
- `0x140014650`
- `0x140014ea0`
- `0x140020154`

## callees

- `0x140008cc0`
- `0x1400159cc`
- `0x140017590`
- `0x140020508`
- `0x1400206e4`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14002073f`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002073f`
- `ntoskrnl!KeReleaseMutex` at `0x14002085e`
- `ntoskrnl!KeReleaseMutex` at `0x14002085e`

## pseudocode

```c
LONG __fastcall HacpRemoveEntry(__int64 *a1)
{
  __int64 v2; // r8
  __int64 v3; // r9
  __int64 v4; // r8
  __int64 v5; // r9
  __int64 *i; // rax
  __int64 v7; // rcx
  _QWORD *v8; // rdi
  _QWORD *v9; // rax
  _DWORD *v10; // rcx
  unsigned int v11; // edx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0 )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_886931b40f7b3ff1a71efc5ba0c73e17_Traceguids);
  KeWaitForSingleObject((PVOID)a1[5], Executive, 0, 0, 0);
  v4 = (unsigned int)HacpHashFunction(*(unsigned int *)(a1[5] + 56), a1 + 8, v2, v3);
  v5 = *(_QWORD *)(a1[5] + 120);
  for ( i = *(__int64 **)(v5 + 8 * v4); i; i = (__int64 *)*i )
  {
    if ( i == a1 )
    {
      v7 = *a1;
      if ( a1 == *(__int64 **)(v5 + 8 * v4) )
      {
        if ( v7 )
          *(_QWORD *)(v7 + 8) = 0;
        v8 = a1 + 1;
        *(_QWORD *)(v5 + 8 * v4) = *a1;
      }
      else
      {
        v8 = a1 + 1;
        v9 = (_QWORD *)a1[1];
        if ( v7 )
        {
          if ( v9 )
          {
            *v9 = v7;
            *(_QWORD *)(*a1 + 8) = *v8;
          }
        }
        else if ( v9 )
        {
          *v9 = 0;
        }
      }
      --*(_DWORD *)(a1[5] + 72);
      v10 = (_DWORD *)a1[5];
      if ( v10[18] < v10[17] )
      {
        v11 = v10[14];
        if ( v11 > v10[15]
          && !(unsigned int)HacpAdjustTable(v10, v11 >> 1, v4, v5)
          && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_886931b40f7b3ff1a71efc5ba0c73e17_Traceguids);
        }
      }
      *((_WORD *)a1 + 24) |= 1u;
      *a1 = 0;
      *v8 = 0;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0 )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_886931b40f7b3ff1a71efc5ba0c73e17_Traceguids);
      }
      return KeReleaseMutex((PRKMUTEX)a1[5], 0);
    }
  }
  return KeReleaseMutex((PRKMUTEX)a1[5], 0);
}

```

## disassembly

```asm
0x1400206e4  mov     [rsp+arg_0], rbx
0x1400206e9  mov     [rsp+arg_8], rbp
0x1400206ee  push    rdi
0x1400206ef  sub     rsp, 30h
0x1400206f3  mov     rbx, rcx
0x1400206f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400206fd  lea     rbp, WPP_GLOBAL_Control
0x140020704  cmp     rcx, rbp
0x140020707  jz      short loc_14002072A
0x140020709  test    dword ptr [rcx+2Ch], 800h
0x140020710  jz      short loc_14002072A
0x140020712  mov     rcx, [rcx+18h]
0x140020716  lea     r8, WPP_886931b40f7b3ff1a71efc5ba0c73e17_Traceguids
0x14002071d  mov     edx, 10h
0x140020722  mov     r9, rbx
0x140020725  call    WPP_SF_q
0x14002072a  mov     rcx, [rbx+28h]; Object
0x14002072e  xor     r9d, r9d; Alertable
0x140020731  xor     r8d, r8d; WaitMode
0x140020734  mov     [rsp+38h+Timeout], 0; Timeout
0x14002073d  xor     edx, edx; WaitReason
0x14002073f  call    cs:__imp_KeWaitForSingleObject
0x140020746  nop     dword ptr [rax+rax+00h]
0x14002074b  mov     rcx, [rbx+28h]
0x14002074f  lea     rdx, [rbx+40h]
0x140020753  mov     ecx, [rcx+38h]
0x140020756  call    HacpHashFunction
0x14002075b  mov     r8d, eax
0x14002075e  mov     rax, [rbx+28h]
0x140020762  mov     r9, [rax+78h]
0x140020766  mov     rdx, [r9+r8*8]
0x14002076a  mov     rax, rdx
0x14002076d  test    rax, rax
0x140020770  jz      loc_140020858
0x140020776  cmp     rax, rbx
0x140020779  jz      short loc_140020780
0x14002077b  mov     rax, [rax]
0x14002077e  jmp     short loc_14002076D
0x140020780  mov     rcx, [rbx]
0x140020783  cmp     rbx, rdx
0x140020786  jnz     short loc_1400207A2
0x140020788  test    rcx, rcx
0x14002078b  jz      short loc_140020795
0x14002078d  mov     qword ptr [rcx+8], 0
0x140020795  mov     rax, [rbx]
0x140020798  lea     rdi, [rbx+8]
0x14002079c  mov     [r9+r8*8], rax
0x1400207a0  jmp     short loc_1400207CA
0x1400207a2  lea     rdi, [rbx+8]
0x1400207a6  mov     rax, [rdi]
0x1400207a9  test    rcx, rcx
0x1400207ac  jnz     short loc_1400207B8
0x1400207ae  test    rax, rax
0x1400207b1  jz      short loc_1400207CA
0x1400207b3  mov     [rax], rcx
0x1400207b6  jmp     short loc_1400207CA
0x1400207b8  test    rax, rax
0x1400207bb  jz      short loc_1400207CA
0x1400207bd  mov     [rax], rcx
0x1400207c0  mov     rcx, [rbx]
0x1400207c3  mov     rax, [rdi]
0x1400207c6  mov     [rcx+8], rax
0x1400207ca  mov     rax, [rbx+28h]
0x1400207ce  dec     dword ptr [rax+48h]
0x1400207d1  mov     rcx, [rbx+28h]
0x1400207d5  mov     eax, [rcx+44h]
0x1400207d8  cmp     [rcx+48h], eax
0x1400207db  jnb     short loc_140020818
0x1400207dd  mov     edx, [rcx+38h]
0x1400207e0  cmp     edx, [rcx+3Ch]
0x1400207e3  jbe     short loc_140020818
0x1400207e5  shr     edx, 1
0x1400207e7  call    HacpAdjustTable
0x1400207ec  test    eax, eax
0x1400207ee  jnz     short loc_140020818
0x1400207f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400207f7  cmp     rcx, rbp
0x1400207fa  jz      short loc_140020818
0x1400207fc  mov     eax, [rcx+2Ch]
0x1400207ff  test    al, 2
0x140020801  jz      short loc_140020818
0x140020803  mov     rcx, [rcx+18h]
0x140020807  lea     r8, WPP_886931b40f7b3ff1a71efc5ba0c73e17_Traceguids
0x14002080e  mov     edx, 11h
0x140020813  call    WPP_SF_
0x140020818  or      word ptr [rbx+30h], 1
0x14002081d  mov     qword ptr [rbx], 0
0x140020824  mov     qword ptr [rdi], 0
0x14002082b  mov     rcx, cs:WPP_GLOBAL_Control
0x140020832  cmp     rcx, rbp
0x140020835  jz      short loc_140020858
0x140020837  test    dword ptr [rcx+2Ch], 800h
0x14002083e  jz      short loc_140020858
0x140020840  mov     rcx, [rcx+18h]
0x140020844  lea     r8, WPP_886931b40f7b3ff1a71efc5ba0c73e17_Traceguids
0x14002084b  mov     edx, 12h
0x140020850  mov     r9, rbx
0x140020853  call    WPP_SF_q
0x140020858  mov     rcx, [rbx+28h]; Mutex
0x14002085c  xor     edx, edx; Wait
0x14002085e  call    cs:__imp_KeReleaseMutex
0x140020865  nop     dword ptr [rax+rax+00h]
0x14002086a  mov     rbx, [rsp+38h+arg_0]
0x14002086f  mov     rbp, [rsp+38h+arg_8]
0x140020874  add     rsp, 30h
0x140020878  pop     rdi
0x140020879  retn
```
