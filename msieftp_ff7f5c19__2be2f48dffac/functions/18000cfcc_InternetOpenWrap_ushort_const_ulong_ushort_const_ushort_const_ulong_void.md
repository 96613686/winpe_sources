# InternetOpenWrap(ushort const *,ulong,ushort const *,ushort const *,ulong,void * *)

- ea: `0x18000cfcc`
- end: `0x18000d01a`
- name: `?InternetOpenWrap@@YAJPEBGK00KPEAPEAX@Z`
- size: `78`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int, const unsigned __int16 *, const unsigned __int16 *, unsigned int, void **)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180018b4c`
- `0x18001fa30`

## callees

- `0x18000cfcc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cffd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cffd`
- `WININET!InternetOpenW` at `0x18000cfe7`
- `WININET!InternetOpenW` at `0x18000cfe7`

## pseudocode

```c
__int64 __fastcall InternetOpenWrap(
        const unsigned __int16 *a1,
        __int64 a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned int a5,
        void **a6)
{
  unsigned int v6; // ebx
  void *v7; // rcx
  signed int LastError; // eax

  v6 = 0;
  v7 = InternetOpenW(L"Microsoft(r) Windows(tm) FTP Folder", 0, 0, 0, 0);
  *a6 = v7;
  if ( !v7 )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  return v6;
}

```

## disassembly

```asm
0x18000cfcc  push    rbx
0x18000cfce  sub     rsp, 30h
0x18000cfd2  xor     ebx, ebx
0x18000cfd4  lea     rcx, szAgent; "Microsoft(r) Windows(tm) FTP Folder"
0x18000cfdb  xor     r9d, r9d; lpszProxyBypass
0x18000cfde  mov     [rsp+38h+dwFlags], ebx; dwFlags
0x18000cfe2  xor     r8d, r8d; lpszProxy
0x18000cfe5  xor     edx, edx; dwAccessType
0x18000cfe7  call    cs:__imp_InternetOpenW
0x18000cfed  mov     rcx, rax
0x18000cff0  mov     rax, [rsp+38h+arg_28]
0x18000cff5  mov     [rax], rcx
0x18000cff8  test    rcx, rcx
0x18000cffb  jnz     short loc_18000D012
0x18000cffd  call    cs:__imp_GetLastError
0x18000d003  mov     ebx, eax
0x18000d005  test    eax, eax
0x18000d007  jle     short loc_18000D012
0x18000d009  movzx   ebx, ax
0x18000d00c  or      ebx, 80070000h
0x18000d012  mov     eax, ebx
0x18000d014  add     rsp, 30h
0x18000d018  pop     rbx
0x18000d019  retn
```
