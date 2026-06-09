# CImportExportCallback::OnAepExportComplete(ulong,uchar const *,long)

- ea: `0x140018720`
- end: `0x140018795`
- name: `?OnAepExportComplete@CImportExportCallback@@UEAAJKPEBEJ@Z`
- size: `117`
- prototype: `__int64 __fastcall(CImportExportCallback *this, unsigned int, const unsigned __int8 *, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x14000cdac`
- `0x140018720`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14001878d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14001878d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140018763`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140018763`

## pseudocode

```c
__int64 __fastcall CImportExportCallback::OnAepExportComplete(
        CImportExportCallback *this,
        unsigned int a2,
        const unsigned __int8 *a3,
        int a4)
{
  unsigned int v8; // ebx

  if ( a4 < 0 )
  {
    if ( a2 || a3 )
      return (unsigned int)-2147024809;
  }
  else if ( !a2 || !a3 )
  {
    return (unsigned int)-2147024809;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  if ( *((_DWORD *)this + 22) )
    v8 = OnAepExportCompleteStub(a2, a3, a4, *((void **)this + 5));
  else
    v8 = -2140930029;
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  return v8;
}

```

## disassembly

```asm
0x140018720  push    rbx
0x140018722  push    rbp
0x140018723  push    rsi
0x140018724  push    rdi
0x140018725  push    r14
0x140018727  sub     rsp, 20h
0x14001872b  mov     r14d, r9d
0x14001872e  mov     rbx, r8
0x140018731  mov     edi, edx
0x140018733  mov     rbp, rcx
0x140018736  test    r9d, r9d
0x140018739  js      short loc_140018756
0x14001873b  test    edx, edx
0x14001873d  jz      short loc_140018744
0x14001873f  test    rbx, rbx
0x140018742  jnz     short loc_14001875F
0x140018744  mov     ebx, 80070057h
0x140018749  mov     eax, ebx
0x14001874b  add     rsp, 20h
0x14001874f  pop     r14
0x140018751  pop     rdi
0x140018752  pop     rsi
0x140018753  pop     rbp
0x140018754  pop     rbx
0x140018755  retn
0x140018756  test    edi, edi
0x140018758  jnz     short loc_140018744
0x14001875a  test    rbx, rbx
0x14001875d  jnz     short loc_140018744
0x14001875f  add     rcx, 30h ; '0'; lpCriticalSection
0x140018763  call    cs:__imp_EnterCriticalSection
0x140018769  cmp     dword ptr [rbp+58h], 0
0x14001876d  jz      short loc_140018784
0x14001876f  mov     r9, [rbp+28h]; void *
0x140018773  mov     r8d, r14d; int
0x140018776  mov     rdx, rbx; Src
0x140018779  mov     ecx, edi; Size
0x14001877b  call    ?OnAepExportCompleteStub@@YAJKPEBEJPEAX@Z; OnAepExportCompleteStub(ulong,uchar const *,long,void *)
0x140018780  mov     ebx, eax
0x140018782  jmp     short loc_140018789
0x140018784  mov     ebx, 80640013h
0x140018789  lea     rcx, [rbp+30h]; lpCriticalSection
0x14001878d  call    cs:__imp_LeaveCriticalSection
0x140018793  jmp     short loc_140018749
```
