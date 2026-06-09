# IDENTITY::~IDENTITY(void)

- ea: `0x18003a82c`
- end: `0x18003a883`
- name: `??1IDENTITY@@QEAA@XZ`
- size: `87`
- prototype: `void __fastcall(IDENTITY *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003a88c`

## callees

- `0x180015594`
- `0x18003a82c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a85b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a866`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a876`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a85b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a866`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a876`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall IDENTITY::~IDENTITY(IDENTITY *this)
{
  const unsigned __int16 *v2; // rcx
  __int64 i; // rdx
  _BYTE *v4; // rcx

  v2 = (const unsigned __int16 *)*((_QWORD *)this + 4);
  if ( v2 )
  {
    for ( i = 2LL * (int)safe_lstrlenW(v2); i; --i )
      *v4++ = 0;
  }
  CoTaskMemFree(*((LPVOID *)this + 4));
  CoTaskMemFree(*((LPVOID *)this + 3));
  if ( *(_DWORD *)this )
    CoTaskMemFree(*((LPVOID *)this + 1));
}

```

## disassembly

```asm
0x18003a82c  push    rbx
0x18003a82e  sub     rsp, 20h
0x18003a832  mov     rbx, rcx
0x18003a835  mov     rcx, [rcx+20h]; unsigned __int16 *
0x18003a839  test    rcx, rcx
0x18003a83c  jz      short loc_18003A857
0x18003a83e  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x18003a843  movsxd  rdx, eax
0x18003a846  add     rdx, rdx
0x18003a849  jz      short loc_18003A857
0x18003a84b  mov     byte ptr [rcx], 0
0x18003a84e  inc     rcx
0x18003a851  sub     rdx, 1
0x18003a855  jnz     short loc_18003A84B
0x18003a857  mov     rcx, [rbx+20h]; pv
0x18003a85b  call    cs:__imp_CoTaskMemFree
0x18003a861  nop
0x18003a862  mov     rcx, [rbx+18h]; pv
0x18003a866  call    cs:__imp_CoTaskMemFree
0x18003a86c  nop
0x18003a86d  cmp     dword ptr [rbx], 0
0x18003a870  jz      short loc_18003A87D
0x18003a872  mov     rcx, [rbx+8]; pv
0x18003a876  call    cs:__imp_CoTaskMemFree
0x18003a87c  nop
0x18003a87d  add     rsp, 20h
0x18003a881  pop     rbx
0x18003a882  retn
```
