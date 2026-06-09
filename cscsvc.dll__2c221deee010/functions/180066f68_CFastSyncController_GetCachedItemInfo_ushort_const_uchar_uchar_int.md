# CFastSyncController::_GetCachedItemInfo(ushort const *,uchar *,uchar *,int *)

- ea: `0x180066f68`
- end: `0x1800670de`
- name: `?_GetCachedItemInfo@CFastSyncController@@IEAAJPEBGPEAE1PEAH@Z`
- size: `374`
- prototype: `__int64 __fastcall(CFastSyncController *this, const unsigned __int16 *, unsigned __int8 *, unsigned __int8 *, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180067188`

## callees

- `0x18000a0d0`
- `0x18001b4e0`
- `0x18001ba60`
- `0x180028f20`
- `0x180039610`
- `0x180039fb4`
- `0x180066f68`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180066fb7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006703d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180066fb7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006703d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180067023`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800670b2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180067023`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800670b2`
- `KERNEL32!CompareStringW` at `0x180066fe3`
- `KERNEL32!CompareStringW` at `0x180066fe3`

## pseudocode

```c
__int64 __fastcall CFastSyncController::_GetCachedItemInfo(
        CFastSyncController *this,
        const unsigned __int16 *a2,
        unsigned __int8 *a3,
        unsigned __int8 *a4,
        int *a5)
{
  struct _RTL_CRITICAL_SECTION *v5; // rsi
  int Item; // edi
  const WCHAR *lpString2; // rax
  int v12; // eax
  unsigned __int8 v13; // r8
  unsigned __int8 v14; // r9
  _QWORD v16[2]; // [rsp+30h] [rbp-368h] BYREF
  _BYTE v17[212]; // [rsp+40h] [rbp-358h] BYREF
  unsigned __int8 v18; // [rsp+114h] [rbp-284h]
  unsigned __int8 v19; // [rsp+115h] [rbp-283h]

  v5 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 1952);
  Item = 0;
  *a3 = 0;
  *a4 = 0;
  *a5 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 1952));
  lpString2 = CPath::_GetConstBuffer((CFastSyncController *)((char *)this + 1368));
  if ( CompareStringW(0x7Fu, 1u, a2, -1, lpString2, -1) == 2 )
  {
    *a3 = *((_BYTE *)this + 1944);
    *a4 = *((_BYTE *)this + 1945);
    *a5 = *((_DWORD *)this + 487);
  }
  else
  {
    memset_0(v17, 0, 0x300u);
    LeaveCriticalSection(v5);
    Item = CscLib_FindItem(a2, 0, (struct tagOFFLINEFILES_ITEM_DESCRIPTOR *)v17);
    EnterCriticalSection(v5);
    if ( Item >= 0 )
    {
      v16[0] = v17;
      v12 = CPath::Copy((CFastSyncController *)((char *)this + 1368), a2);
      v13 = v19;
      v14 = v18;
      if ( v12 >= 0 )
      {
        *((_BYTE *)this + 1944) = v18;
        *((_BYTE *)this + 1945) = v13;
        *((_DWORD *)this + 487) = CCacheItemInfo::IsItemFile((CCacheItemInfo *)v16) == 0;
      }
      *a3 = v14;
      *a4 = v13;
      *a5 = CCacheItemInfo::IsItemFile((CCacheItemInfo *)v16) == 0;
    }
  }
  LeaveCriticalSection(v5);
  return (unsigned int)Item;
}

```

## disassembly

```asm
0x180066f68  push    rbx
0x180066f6a  push    rbp
0x180066f6b  push    rsi
0x180066f6c  push    rdi
0x180066f6d  push    r12
0x180066f6f  push    r13
0x180066f71  push    r14
0x180066f73  push    r15
0x180066f75  sub     rsp, 358h
0x180066f7c  mov     rax, cs:__security_cookie
0x180066f83  xor     rax, rsp
0x180066f86  mov     [rsp+398h+var_58], rax
0x180066f8e  mov     rbp, [rsp+398h+arg_20]
0x180066f96  lea     rsi, [rcx+7A0h]
0x180066f9d  xor     edi, edi
0x180066f9f  mov     rbx, rcx
0x180066fa2  mov     [r8], dil
0x180066fa5  mov     rcx, rsi; lpCriticalSection
0x180066fa8  mov     [r9], dil
0x180066fab  mov     r15, r9
0x180066fae  mov     [rbp+0], edi
0x180066fb1  mov     r14, r8
0x180066fb4  mov     r12, rdx
0x180066fb7  call    cs:__imp_EnterCriticalSection
0x180066fbd  lea     r13, [rbx+558h]
0x180066fc4  mov     rcx, r13; this
0x180066fc7  call    ?_GetConstBuffer@CPath@@AEBAPEBGXZ; CPath::_GetConstBuffer(void)
0x180066fcc  or      r9d, 0FFFFFFFFh; cchCount1
0x180066fd0  lea     edx, [rdi+1]; dwCmpFlags
0x180066fd3  mov     [rsp+398h+cchCount2], r9d; cchCount2
0x180066fd8  lea     ecx, [rdi+7Fh]; Locale
0x180066fdb  mov     r8, r12; lpString1
0x180066fde  mov     [rsp+398h+lpString2], rax; lpString2
0x180066fe3  call    cs:__imp_CompareStringW
0x180066fe9  cmp     eax, 2
0x180066fec  jnz     short loc_18006700E
0x180066fee  mov     al, [rbx+798h]
0x180066ff4  mov     [r14], al
0x180066ff7  mov     al, [rbx+799h]
0x180066ffd  mov     [r15], al
0x180067000  mov     eax, [rbx+79Ch]
0x180067006  mov     [rbp+0], eax
0x180067009  jmp     loc_1800670AF
0x18006700e  xor     edx, edx; Val
0x180067010  lea     rcx, [rsp+398h+var_358]; void *
0x180067015  mov     r8d, 300h; Size
0x18006701b  call    memset_0
0x180067020  mov     rcx, rsi; lpCriticalSection
0x180067023  call    cs:__imp_LeaveCriticalSection
0x180067029  lea     r8, [rsp+398h+var_358]; struct tagOFFLINEFILES_ITEM_DESCRIPTOR *
0x18006702e  xor     edx, edx; unsigned int
0x180067030  mov     rcx, r12; SourceString
0x180067033  call    ?CscLib_FindItem@@YAJPEBGKPEAUtagOFFLINEFILES_ITEM_DESCRIPTOR@@@Z; CscLib_FindItem(ushort const *,ulong,tagOFFLINEFILES_ITEM_DESCRIPTOR *)
0x180067038  mov     rcx, rsi; lpCriticalSection
0x18006703b  mov     edi, eax
0x18006703d  call    cs:__imp_EnterCriticalSection
0x180067043  test    edi, edi
0x180067045  js      short loc_1800670AF
0x180067047  lea     rax, [rsp+398h+var_358]
0x18006704c  mov     rdx, r12; unsigned __int16 *
0x18006704f  mov     rcx, r13; this
0x180067052  mov     [rsp+398h+var_368], rax
0x180067057  call    ?Copy@CPath@@QEAAJPEBG@Z; CPath::Copy(ushort const *)
0x18006705c  mov     r8b, [rsp+398h+var_283]
0x180067064  mov     r9b, [rsp+398h+var_284]
0x18006706c  test    eax, eax
0x18006706e  js      short loc_180067095
0x180067070  lea     rcx, [rsp+398h+var_368]; this
0x180067075  mov     [rbx+798h], r9b
0x18006707c  mov     [rbx+799h], r8b
0x180067083  call    ?IsItemFile@CCacheItemInfo@@QEBAHXZ; CCacheItemInfo::IsItemFile(void)
0x180067088  xor     edx, edx
0x18006708a  test    eax, eax
0x18006708c  setz    dl
0x18006708f  mov     [rbx+79Ch], edx
0x180067095  mov     [r14], r9b
0x180067098  lea     rcx, [rsp+398h+var_368]; this
0x18006709d  mov     [r15], r8b
0x1800670a0  call    ?IsItemFile@CCacheItemInfo@@QEBAHXZ; CCacheItemInfo::IsItemFile(void)
0x1800670a5  xor     edx, edx
0x1800670a7  test    eax, eax
0x1800670a9  setz    dl
0x1800670ac  mov     [rbp+0], edx
0x1800670af  mov     rcx, rsi; lpCriticalSection
0x1800670b2  call    cs:__imp_LeaveCriticalSection
0x1800670b8  mov     eax, edi
0x1800670ba  mov     rcx, [rsp+398h+var_58]
0x1800670c2  xor     rcx, rsp; StackCookie
0x1800670c5  call    __security_check_cookie
0x1800670ca  add     rsp, 358h
0x1800670d1  pop     r15
0x1800670d3  pop     r14
0x1800670d5  pop     r13
0x1800670d7  pop     r12
0x1800670d9  pop     rdi
0x1800670da  pop     rsi
0x1800670db  pop     rbp
0x1800670dc  pop     rbx
0x1800670dd  retn
```
