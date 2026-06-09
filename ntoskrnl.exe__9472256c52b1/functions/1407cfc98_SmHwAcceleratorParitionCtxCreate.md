# SmHwAcceleratorParitionCtxCreate

- ea: `0x1407cfc98`
- end: `0x1407cfec6`
- name: `SmHwAcceleratorParitionCtxCreate`
- size: `558`
- prototype: `__int64 __fastcall(_QWORD *, __int64, int)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x140742ef4`

## callees

- `0x1402a3fe0`
- `0x1402a4070`
- `0x1402a5f60`
- `0x1404440b0`
- `0x1406eac40`
- `0x1406f7380`
- `0x1407cfc98`
- `0x1407cffe4`

## import_xrefs

- `ext-ms-win-accel-api-km-l1-1-1!AccelShareAddressSpaceWithResource` at `0x1407cfcf0`
- `ext-ms-win-accel-api-km-l1-1-1!AccelShareAddressSpaceWithResource` at `0x1407cfcf0`
- `ext-ms-win-accel-api-km-l1-1-1!AccelStopSharingAddressSpaceWithResource` at `0x1407cfe92`
- `ext-ms-win-accel-api-km-l1-1-1!AccelStopSharingAddressSpaceWithResource` at `0x1407cfe92`

## pseudocode

```c
__int64 __fastcall SmHwAcceleratorParitionCtxCreate(_QWORD *a1, __int64 a2, int a3)
{
  struct _EX_RUNDOWN_REF *v3; // r12
  __int64 v4; // rsi
  BOOLEAN v6; // al
  __int64 v7; // rdx
  int v8; // r14d
  int v9; // ebx
  __int64 v10; // r8
  __int64 v11; // rcx
  __int64 v12; // rbx
  int v13; // eax
  __int64 v14; // r8
  __int64 v15; // r15
  unsigned __int64 v16; // rbx
  char *v17; // rax
  char *v18; // rbp
  unsigned __int64 v19; // r14
  char *v20; // rdx
  char *v21; // r14
  _SLIST_ENTRY *v22; // r15
  struct _SLIST_ENTRY *v23; // rbx
  unsigned __int64 v24; // r12
  unsigned __int64 v26; // [rsp+20h] [rbp-58h]
  char *v27; // [rsp+20h] [rbp-58h]
  ULONG Count; // [rsp+28h] [rbp-50h]
  struct _SLIST_ENTRY *List; // [rsp+30h] [rbp-48h]
  __int64 v31; // [rsp+88h] [rbp+10h] BYREF
  unsigned __int64 v32; // [rsp+98h] [rbp+20h]

  v3 = (struct _EX_RUNDOWN_REF *)(a2 + 32);
  v4 = a3;
  v31 = 0;
  v6 = ExAcquireRundownProtection_0((PEX_RUNDOWN_REF)(a2 + 32));
  v8 = v6;
  if ( !v6 )
  {
    v9 = -1073741431;
    goto LABEL_14;
  }
  if ( (_DWORD)v4 )
  {
    v10 = v4;
  }
  else
  {
    LOBYTE(v7) = 1;
    v9 = AccelShareAddressSpaceWithResource(*(_QWORD *)(a2 + 16), v7, &v31);
    if ( v9 < 0 )
      goto LABEL_14;
    v10 = 0;
  }
  v11 = *(unsigned int *)(a2 + 64);
  v12 = *(unsigned int *)(a2 + 4 * v10 + 56);
  v13 = *(_DWORD *)(a2 + 4 * v10 + 48) - 1;
  v14 = *(unsigned int *)(a2 + 44);
  v15 = ((int)v11 + v13) / (unsigned int)v11;
  LODWORD(v14) = v14 | 0x80000000;
  Count = ((int)v11 + v13) / (unsigned int)v11;
  v16 = (v15 * v11 * v12 + 95) & 0xFFFFFFFFFFFFFFF0uLL;
  v32 = ((unsigned int)(*(_DWORD *)(a2 + 40) * *(_DWORD *)(a2 + 64)) + 47LL) & 0xFFFFFFFFFFFFFFF0uLL;
  v26 = v32 * (unsigned int)v15;
  v17 = (char *)SmAllocEx(v16 + v26, 1665232243, v14);
  v18 = v17;
  if ( v17 )
  {
    memset_0(v17, 0, 0x50u);
    v19 = v32;
    v20 = &v18[v16 + v26];
    *((_DWORD *)v18 + 14) = v15;
    v21 = &v18[v16 + v19];
    *((_QWORD *)v18 + 4) = a2;
    v22 = (_SLIST_ENTRY *)(v18 + 80);
    *((_DWORD *)v18 + 15) = v4;
    v23 = (struct _SLIST_ENTRY *)&v18[v16];
    *((_QWORD *)v18 + 5) = v31;
    *((_QWORD *)v18 + 6) = 0;
    List = v23;
    v27 = v20;
    if ( v21 < v20 )
    {
      v24 = v32;
      do
      {
        v23->Next = (_SLIST_ENTRY *)v21;
        *((_QWORD *)&v23->Next + 1) = v18;
        v23[1].Next = v22;
        SmHwInitializeAccelDescriptor(v23, a2, (unsigned int)v4);
        v23 = (struct _SLIST_ENTRY *)v21;
        v21 += v24;
        v22 = (_SLIST_ENTRY *)((char *)v22 + (unsigned int)(*(_DWORD *)(a2 + 64) * *(_DWORD *)(a2 + 4 * v4 + 56)));
      }
      while ( v21 < v27 );
      v3 = (struct _EX_RUNDOWN_REF *)(a2 + 32);
    }
    v23->Next = 0;
    *((_QWORD *)&v23->Next + 1) = v18;
    v23[1].Next = v22;
    SmHwInitializeAccelDescriptor(v23, a2, (unsigned int)v4);
    InterlockedPushListSList((PSLIST_HEADER)v18 + 1, List, v23, Count);
    ExAcquireRundownProtectionEx((PEX_RUNDOWN_REF)v18 + 6, Count);
    _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)v18 + 4) + 68LL));
    v8 = 0;
    v31 = 0;
    v9 = 0;
    *a1 = v18;
  }
  else
  {
    v9 = -1073741670;
  }
LABEL_14:
  if ( v31 )
    AccelStopSharingAddressSpaceWithResource();
  if ( v8 )
    ExReleaseRundownProtection_0(v3);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1407cfc98  mov     rax, rsp
0x1407cfc9b  mov     [rax+18h], rbx
0x1407cfc9f  mov     [rax+8], rcx
0x1407cfca3  push    rbp
0x1407cfca4  push    rsi
0x1407cfca5  push    rdi
0x1407cfca6  push    r12
0x1407cfca8  push    r13
0x1407cfcaa  push    r14
0x1407cfcac  push    r15
0x1407cfcae  sub     rsp, 40h
0x1407cfcb2  lea     r12, [rdx+20h]
0x1407cfcb6  movsxd  rsi, r8d
0x1407cfcb9  mov     rcx, r12; RunRef
0x1407cfcbc  mov     qword ptr [rax+10h], 0
0x1407cfcc4  mov     rdi, rdx
0x1407cfcc7  call    ExAcquireRundownProtection_0
0x1407cfccc  movzx   r14d, al
0x1407cfcd0  test    al, al
0x1407cfcd2  jnz     short loc_1407CFCDE
0x1407cfcd4  mov     ebx, 0C0000189h
0x1407cfcd9  jmp     loc_1407CFE85
0x1407cfcde  test    esi, esi
0x1407cfce0  jnz     short loc_1407CFD0B
0x1407cfce2  mov     rcx, [rdi+10h]
0x1407cfce6  lea     r8, [rsp+78h+arg_8]
0x1407cfcee  mov     dl, 1
0x1407cfcf0  call    cs:__imp_AccelShareAddressSpaceWithResource
0x1407cfcf7  nop     dword ptr [rax+rax+00h]
0x1407cfcfc  mov     ebx, eax
0x1407cfcfe  test    eax, eax
0x1407cfd00  js      loc_1407CFE85
0x1407cfd06  xor     r8d, r8d
0x1407cfd09  jmp     short loc_1407CFD0E
0x1407cfd0b  mov     r8, rsi
0x1407cfd0e  mov     ecx, [rdi+40h]
0x1407cfd11  xor     edx, edx
0x1407cfd13  mov     eax, [rdi+r8*4+30h]
0x1407cfd18  mov     r13, rsi
0x1407cfd1b  mov     ebx, [rdi+r8*4+38h]
0x1407cfd20  dec     eax
0x1407cfd22  mov     r8d, [rdi+2Ch]
0x1407cfd26  add     eax, ecx
0x1407cfd28  div     ecx
0x1407cfd2a  imul    rbx, rcx
0x1407cfd2e  mov     r15d, eax
0x1407cfd31  bts     r8d, 1Fh
0x1407cfd36  mov     eax, ecx
0x1407cfd38  mov     qword ptr [rsp+78h+Count], r15
0x1407cfd3d  imul    eax, [rdi+28h]
0x1407cfd41  mov     ecx, r15d
0x1407cfd44  imul    rbx, r15
0x1407cfd48  add     rax, 2Fh ; '/'
0x1407cfd4c  mov     edx, 63416D73h
0x1407cfd51  and     rax, 0FFFFFFFFFFFFFFF0h
0x1407cfd55  add     rbx, 5Fh ; '_'
0x1407cfd59  imul    rcx, rax
0x1407cfd5d  and     rbx, 0FFFFFFFFFFFFFFF0h
0x1407cfd61  mov     [rsp+78h+arg_18], rax
0x1407cfd69  mov     [rsp+78h+var_58], rcx
0x1407cfd6e  add     rcx, rbx
0x1407cfd71  call    SmAllocEx
0x1407cfd76  mov     rbp, rax
0x1407cfd79  test    rax, rax
0x1407cfd7c  jnz     short loc_1407CFD88
0x1407cfd7e  mov     ebx, 0C000009Ah
0x1407cfd83  jmp     loc_1407CFE85
0x1407cfd88  xor     edx, edx; Val
0x1407cfd8a  mov     rcx, rbp; void *
0x1407cfd8d  lea     r8d, [rdx+50h]; Size
0x1407cfd91  call    memset_0
0x1407cfd96  mov     rdx, [rsp+78h+var_58]
0x1407cfd9b  lea     rcx, [rbx+rbp]
0x1407cfd9f  mov     r14, [rsp+78h+arg_18]
0x1407cfda7  add     rdx, rcx
0x1407cfdaa  mov     [rbp+38h], r15d
0x1407cfdae  add     r14, rcx
0x1407cfdb1  mov     [rbp+20h], rdi
0x1407cfdb5  lea     r15, [rbp+50h]
0x1407cfdb9  mov     [rbp+3Ch], esi
0x1407cfdbc  mov     rbx, rcx
0x1407cfdbf  mov     rax, [rsp+78h+arg_8]
0x1407cfdc7  mov     [rbp+28h], rax
0x1407cfdcb  mov     qword ptr [rbp+30h], 0
0x1407cfdd3  mov     [rsp+78h+List], rcx
0x1407cfdd8  mov     [rsp+78h+var_58], rdx
0x1407cfddd  cmp     r14, rdx
0x1407cfde0  jnb     short loc_1407CFE20
0x1407cfde2  mov     r12, [rsp+78h+arg_18]
0x1407cfdea  mov     r8d, esi
0x1407cfded  mov     [rbx], r14
0x1407cfdf0  mov     rdx, rdi
0x1407cfdf3  mov     [rbx+8], rbp
0x1407cfdf7  mov     rcx, rbx
0x1407cfdfa  mov     [rbx+10h], r15
0x1407cfdfe  call    SmHwInitializeAccelDescriptor
0x1407cfe03  mov     eax, [rdi+r13*4+38h]
0x1407cfe08  mov     rbx, r14
0x1407cfe0b  imul    eax, [rdi+40h]
0x1407cfe0f  add     r14, r12
0x1407cfe12  add     r15, rax
0x1407cfe15  cmp     r14, [rsp+78h+var_58]
0x1407cfe1a  jb      short loc_1407CFDEA
0x1407cfe1c  lea     r12, [rdi+20h]
0x1407cfe20  mov     r8d, esi
0x1407cfe23  mov     qword ptr [rbx], 0
0x1407cfe2a  mov     rdx, rdi
0x1407cfe2d  mov     [rbx+8], rbp
0x1407cfe31  mov     rcx, rbx
0x1407cfe34  mov     [rbx+10h], r15
0x1407cfe38  call    SmHwInitializeAccelDescriptor
0x1407cfe3d  mov     rdi, qword ptr [rsp+78h+Count]
0x1407cfe42  lea     rcx, [rbp+10h]; ListHead
0x1407cfe46  mov     rdx, [rsp+78h+List]; List
0x1407cfe4b  mov     r9d, edi; Count
0x1407cfe4e  mov     r8, rbx; ListEnd
0x1407cfe51  call    InterlockedPushListSList
0x1407cfe56  mov     edx, edi; Count
0x1407cfe58  lea     rcx, [rbp+30h]; RunRef
0x1407cfe5c  call    ExAcquireRundownProtectionEx
0x1407cfe61  mov     rax, [rbp+20h]
0x1407cfe65  lock inc dword ptr [rax+44h]
0x1407cfe69  mov     rax, [rsp+78h+arg_0]
0x1407cfe71  xor     r14d, r14d
0x1407cfe74  mov     [rsp+78h+arg_8], 0
0x1407cfe80  xor     ebx, ebx
0x1407cfe82  mov     [rax], rbp
0x1407cfe85  mov     rcx, [rsp+78h+arg_8]
0x1407cfe8d  test    rcx, rcx
0x1407cfe90  jz      short loc_1407CFE9E
0x1407cfe92  call    cs:__imp_AccelStopSharingAddressSpaceWithResource
0x1407cfe99  nop     dword ptr [rax+rax+00h]
0x1407cfe9e  test    r14d, r14d
0x1407cfea1  jz      short loc_1407CFEAB
0x1407cfea3  mov     rcx, r12; RunRef
0x1407cfea6  call    ExReleaseRundownProtection_0
0x1407cfeab  mov     eax, ebx
0x1407cfead  mov     rbx, [rsp+78h+arg_10]
0x1407cfeb5  add     rsp, 40h
0x1407cfeb9  pop     r15
0x1407cfebb  pop     r14
0x1407cfebd  pop     r13
0x1407cfebf  pop     r12
0x1407cfec1  pop     rdi
0x1407cfec2  pop     rsi
0x1407cfec3  pop     rbp
0x1407cfec4  retn
```
