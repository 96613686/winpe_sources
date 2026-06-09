# NetiopCreatevSwitchForwardFlow

- ea: `0x140074330`
- end: `0x14007456b`
- name: `NetiopCreatevSwitchForwardFlow`
- size: `571`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140073c10`

## callees

- `0x140017520`
- `0x1400176d0`
- `0x140030a08`
- `0x14003a130`
- `0x140074330`

## import_xrefs

- `ntoskrnl!RtlInsertEntryHashTable` at `0x140074508`
- `ntoskrnl!RtlInsertEntryHashTable` at `0x140074540`
- `ntoskrnl!RtlInsertEntryHashTable` at `0x140074508`
- `ntoskrnl!RtlInsertEntryHashTable` at `0x140074540`
- `ntoskrnl!RtlCreateHashTable` at `0x1400743a1`
- `ntoskrnl!RtlCreateHashTable` at `0x1400743a1`
- `ntoskrnl!KeInitializeSpinLock` at `0x140074495`
- `ntoskrnl!KeInitializeSpinLock` at `0x140074495`

## pseudocode

```c
_DWORD *__fastcall NetiopCreatevSwitchForwardFlow(
        __int64 a1,
        __int16 a2,
        _DWORD *a3,
        _DWORD *a4,
        int a5,
        __int16 a6,
        __int16 a7,
        int a8,
        int a9,
        int a10,
        __int64 a11,
        signed __int64 *a12)
{
  __int64 v14; // rax
  __int64 v17; // rbx
  _DWORD *v18; // rdi
  ULONG v20; // edx
  __int64 v21; // rcx
  __int64 v22; // rax
  signed __int64 v23; // rbx
  PRTL_DYNAMIC_HASH_TABLE HashTable; // [rsp+20h] [rbp-48h] BYREF
  signed __int64 v25[8]; // [rsp+28h] [rbp-40h] BYREF

  v14 = 1888;
  if ( a2 != 2 )
    v14 = 1896;
  v17 = *(_QWORD *)(v14 + a1);
  v18 = (_DWORD *)PplAllocateFromLookasideList(v17);
  if ( !v18 )
    return 0;
  if ( a12 && !*(_QWORD *)(a1 + 80) )
  {
    v20 = *(_DWORD *)(a1 + 88);
    HashTable = 0;
    if ( !RtlCreateHashTable(&HashTable, v20, 0) )
    {
      PplFreeToLookasideList(v17, v18);
      return 0;
    }
    *(_QWORD *)(a1 + 80) = HashTable;
  }
  *v18 = 2;
  v21 = 0;
  *((_WORD *)v18 + 4) = a2;
  v18[34] = a10;
  v18[4] = 0;
  do
  {
    *(_QWORD *)&v18[4 * v21 + 46] = 0;
    v22 = 2 * (v21 + 12);
    ++v21;
    *(_QWORD *)&v18[2 * v22] = 0;
  }
  while ( v21 != 3 );
  v18[3] = a5;
  *((_WORD *)v18 + 20) = a6;
  *((_WORD *)v18 + 21) = a7;
  v18[12] = a8;
  v18[13] = a9;
  if ( a2 == 2 )
  {
    v18[59] = *a4;
    v18[58] = *a3;
  }
  else
  {
    *(_OWORD *)(v18 + 62) = *(_OWORD *)a4;
    *(_OWORD *)(v18 + 58) = *(_OWORD *)a3;
  }
  *(_OWORD *)(v18 + 38) = 0;
  *((_QWORD *)v18 + 21) = 0;
  KeInitializeSpinLock((PKSPIN_LOCK)v18 + 18);
  *((_QWORD *)v18 + 20) = v18 + 38;
  *((_QWORD *)v18 + 19) = v18 + 38;
  v18[44] = 2;
  if ( a12 )
  {
    v23 = _InterlockedIncrement64((volatile signed __int64 *)(a1 + 1904));
    HashTable = 0;
    v25[0] = v23;
    NetiopUpdateFlowHashSignature(v25, 8, &HashTable);
    RtlInsertEntryHashTable(
      *(PRTL_DYNAMIC_HASH_TABLE *)(a1 + 80),
      (PRTL_DYNAMIC_HASH_TABLE_ENTRY)(v18 + 26),
      ((_QWORD)HashTable << *(_DWORD *)(a1 + 88)) | 1LL,
      0);
    v18[4] |= 0x10u;
    RoReferenceEx(v18 + 44);
    *a12 = v23;
  }
  RtlInsertEntryHashTable(
    (PRTL_DYNAMIC_HASH_TABLE)(a1 + 16),
    (PRTL_DYNAMIC_HASH_TABLE_ENTRY)(v18 + 14),
    (a11 << *(_DWORD *)(a1 + 56)) | 2,
    0);
  v18[4] |= 4u;
  RoReferenceEx(v18 + 44);
  return v18;
}

```

## disassembly

```asm
0x140074330  push    rbx
0x140074332  push    rbp
0x140074333  push    rsi
0x140074334  push    rdi
0x140074335  push    r12
0x140074337  push    r14
0x140074339  push    r15
0x14007433b  sub     rsp, 30h
0x14007433f  mov     rsi, rcx
0x140074342  movzx   ebp, dx
0x140074345  mov     eax, 760h
0x14007434a  mov     edx, 2
0x14007434f  cmp     bp, dx
0x140074352  mov     r14, r9
0x140074355  mov     r12, r8
0x140074358  lea     ecx, [rax+8]
0x14007435b  cmovnz  eax, ecx
0x14007435e  mov     rbx, [rax+rsi]
0x140074362  mov     rcx, rbx
0x140074365  call    PplAllocateFromLookasideList
0x14007436a  mov     rdi, rax
0x14007436d  test    rax, rax
0x140074370  jnz     short loc_140074379
0x140074372  xor     eax, eax
0x140074374  jmp     loc_14007455B
0x140074379  mov     r15, [rsp+68h+arg_58]
0x140074381  test    r15, r15
0x140074384  jz      short loc_1400743C7
0x140074386  cmp     qword ptr [rsi+50h], 0
0x14007438b  jnz     short loc_1400743C7
0x14007438d  mov     edx, [rsi+58h]; Shift
0x140074390  lea     rcx, [rsp+68h+HashTable]; HashTable
0x140074395  xor     r8d, r8d; Flags
0x140074398  mov     [rsp+68h+HashTable], 0
0x1400743a1  call    cs:__imp_RtlCreateHashTable
0x1400743a8  nop     dword ptr [rax+rax+00h]
0x1400743ad  test    al, al
0x1400743af  jnz     short loc_1400743BE
0x1400743b1  mov     rdx, rdi
0x1400743b4  mov     rcx, rbx
0x1400743b7  call    PplFreeToLookasideList
0x1400743bc  jmp     short loc_140074372
0x1400743be  mov     rax, [rsp+68h+HashTable]
0x1400743c3  mov     [rsi+50h], rax
0x1400743c7  mov     eax, [rsp+68h+arg_48]
0x1400743ce  mov     edx, 2
0x1400743d3  mov     [rdi], edx
0x1400743d5  xor     ecx, ecx
0x1400743d7  mov     [rdi+8], bp
0x1400743db  mov     [rdi+88h], eax
0x1400743e1  mov     dword ptr [rdi+10h], 0
0x1400743e8  mov     rax, rcx
0x1400743eb  add     rax, rax
0x1400743ee  mov     qword ptr [rdi+rax*8+0B8h], 0
0x1400743fa  lea     rax, [rcx+0Ch]
0x1400743fe  add     rax, rax
0x140074401  inc     rcx
0x140074404  mov     qword ptr [rdi+rax*8], 0
0x14007440c  cmp     rcx, 3
0x140074410  jnz     short loc_1400743E8
0x140074412  mov     eax, [rsp+68h+arg_20]
0x140074419  mov     [rdi+0Ch], eax
0x14007441c  movzx   eax, [rsp+68h+arg_28]
0x140074424  mov     [rdi+28h], ax
0x140074428  movzx   eax, [rsp+68h+arg_30]
0x140074430  mov     [rdi+2Ah], ax
0x140074434  mov     eax, [rsp+68h+arg_38]
0x14007443b  mov     [rdi+30h], eax
0x14007443e  mov     eax, [rsp+68h+arg_40]
0x140074445  mov     [rdi+34h], eax
0x140074448  cmp     bp, dx
0x14007444b  jnz     short loc_140074462
0x14007444d  mov     eax, [r14]
0x140074450  mov     [rdi+0ECh], eax
0x140074456  mov     eax, [r12]
0x14007445a  mov     [rdi+0E8h], eax
0x140074460  jmp     short loc_14007447B
0x140074462  movups  xmm0, xmmword ptr [r14]
0x140074466  movdqu  xmmword ptr [rdi+0F8h], xmm0
0x14007446e  movups  xmm1, xmmword ptr [r12]
0x140074473  movdqu  xmmword ptr [rdi+0E8h], xmm1
0x14007447b  lea     rbx, [rdi+98h]
0x140074482  xorps   xmm0, xmm0
0x140074485  xor     eax, eax
0x140074487  lea     rcx, [rdi+90h]; SpinLock
0x14007448e  movups  xmmword ptr [rbx], xmm0
0x140074491  mov     [rbx+10h], rax
0x140074495  call    cs:__imp_KeInitializeSpinLock
0x14007449c  nop     dword ptr [rax+rax+00h]
0x1400744a1  mov     [rbx+8], rbx
0x1400744a5  lea     r14, [rdi+0B0h]
0x1400744ac  mov     [rbx], rbx
0x1400744af  mov     dword ptr [r14], 2
0x1400744b6  test    r15, r15
0x1400744b9  jz      short loc_140074523
0x1400744bb  mov     ebx, 1
0x1400744c0  lock xadd [rsi+770h], rbx
0x1400744c9  inc     rbx
0x1400744cc  mov     [rsp+68h+HashTable], 0
0x1400744d5  lea     r8, [rsp+68h+HashTable]
0x1400744da  mov     [rsp+68h+var_40], rbx
0x1400744df  mov     edx, 8
0x1400744e4  lea     rcx, [rsp+68h+var_40]
0x1400744e9  call    NetiopUpdateFlowHashSignature
0x1400744ee  mov     ecx, [rsi+58h]
0x1400744f1  lea     rdx, [rdi+68h]; Entry
0x1400744f5  mov     r8, [rsp+68h+HashTable]
0x1400744fa  xor     r9d, r9d; Context
0x1400744fd  shl     r8, cl
0x140074500  mov     rcx, [rsi+50h]; HashTable
0x140074504  or      r8, 1; Signature
0x140074508  call    cs:__imp_RtlInsertEntryHashTable
0x14007450f  nop     dword ptr [rax+rax+00h]
0x140074514  or      dword ptr [rdi+10h], 10h
0x140074518  mov     rcx, r14
0x14007451b  call    RoReferenceEx
0x140074520  mov     [r15], rbx
0x140074523  mov     ecx, [rsi+38h]
0x140074526  lea     rdx, [rdi+38h]; Entry
0x14007452a  mov     r8, [rsp+68h+arg_50]
0x140074532  xor     r9d, r9d; Context
0x140074535  shl     r8, cl
0x140074538  lea     rcx, [rsi+10h]; HashTable
0x14007453c  or      r8, 2; Signature
0x140074540  call    cs:__imp_RtlInsertEntryHashTable
0x140074547  nop     dword ptr [rax+rax+00h]
0x14007454c  or      dword ptr [rdi+10h], 4
0x140074550  mov     rcx, r14
0x140074553  call    RoReferenceEx
0x140074558  mov     rax, rdi
0x14007455b  add     rsp, 30h
0x14007455f  pop     r15
0x140074561  pop     r14
0x140074563  pop     r12
0x140074565  pop     rdi
0x140074566  pop     rsi
0x140074567  pop     rbp
0x140074568  pop     rbx
0x140074569  retn
```
