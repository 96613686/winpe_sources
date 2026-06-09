# LoadResourceString(HINSTANCE__ *,ulong,STBUFF *,ulong *)

- ea: `0x180001cd4`
- end: `0x180001dc0`
- name: `?LoadResourceString@@YAJPEAUHINSTANCE__@@KPEAVSTBUFF@@PEAK@Z`
- size: `236`
- prototype: `int(HINSTANCE, unsigned int, struct STBUFF *, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800047a4`

## callees

- `0x180001948`
- `0x180001a2c`
- `0x180001cd4`
- `0x1800067c0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001d95`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001d95`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001d19`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001d19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001d3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001d65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001d3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001d65`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180001d2c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180001d2c`

## pseudocode

```c
__int64 __fastcall LoadResourceString(HINSTANCE a1, UINT a2, struct STBUFF *a3, unsigned int *a4)
{
  HINSTANCE v4; // rbx
  int StringW; // eax
  unsigned int v9; // edi
  int appended; // ebx
  signed int LastError; // eax
  WCHAR Buffer[8]; // [rsp+20h] [rbp-98h] BYREF
  void **v14; // [rsp+30h] [rbp-88h] BYREF
  HLOCAL hMem; // [rsp+38h] [rbp-80h]
  char v16; // [rsp+4Ch] [rbp-6Ch] BYREF

  v4 = g_hModule;
  *(_QWORD *)Buffer = 0;
  STBUFF::STBUFF((STBUFF *)&v14);
  SetLastError(0);
  StringW = LoadStringW(v4, a2, Buffer, 0);
  v9 = StringW;
  if ( !StringW || StringW == -1 && GetLastError() )
  {
    LastError = GetLastError();
    appended = LastError;
    if ( LastError > 0 )
      appended = (unsigned __int16)LastError | 0x80070000;
  }
  else
  {
    appended = STBUFF::AppendData(a3, *(_BYTE **)Buffer, 2 * v9, 0);
    if ( appended >= 0 )
      *a4 = v9;
  }
  v14 = &STBUFF::`vftable';
  if ( hMem != &v16 )
    LocalFree(hMem);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x180001cd4  mov     [rsp+arg_0], rbx
0x180001cd9  push    rbp
0x180001cda  push    rsi
0x180001cdb  push    rdi
0x180001cdc  sub     rsp, 0A0h
0x180001ce3  mov     rax, cs:__security_cookie
0x180001cea  xor     rax, rsp
0x180001ced  mov     [rsp+0B8h+var_28], rax
0x180001cf5  mov     rbx, cs:?g_hModule@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hModule
0x180001cfc  lea     rcx, [rsp+0B8h+var_88]; this
0x180001d01  mov     rsi, r9
0x180001d04  mov     qword ptr [rsp+0B8h+Buffer], 0
0x180001d0d  mov     rbp, r8
0x180001d10  mov     edi, edx
0x180001d12  call    ??0STBUFF@@QEAA@H@Z; STBUFF::STBUFF(int)
0x180001d17  xor     ecx, ecx; dwErrCode
0x180001d19  call    cs:__imp_SetLastError
0x180001d1f  xor     r9d, r9d; cchBufferMax
0x180001d22  lea     r8, [rsp+0B8h+Buffer]; lpBuffer
0x180001d27  mov     edx, edi; uID
0x180001d29  mov     rcx, rbx; hInstance
0x180001d2c  call    cs:__imp_LoadStringW
0x180001d32  mov     edi, eax
0x180001d34  test    eax, eax
0x180001d36  jz      short loc_180001D65
0x180001d38  cmp     eax, 0FFFFFFFFh
0x180001d3b  jnz     short loc_180001D47
0x180001d3d  call    cs:__imp_GetLastError
0x180001d43  test    eax, eax
0x180001d45  jnz     short loc_180001D65
0x180001d47  mov     rdx, qword ptr [rsp+0B8h+Buffer]; void *
0x180001d4c  lea     r8d, [rdi+rdi]; unsigned int
0x180001d50  xor     r9d, r9d; unsigned int
0x180001d53  mov     rcx, rbp; this
0x180001d56  call    ?AppendData@STBUFF@@QEAAJPEAXKK@Z; STBUFF::AppendData(void *,ulong,ulong)
0x180001d5b  mov     ebx, eax
0x180001d5d  test    eax, eax
0x180001d5f  js      short loc_180001D7A
0x180001d61  mov     [rsi], edi
0x180001d63  jmp     short loc_180001D7A
0x180001d65  call    cs:__imp_GetLastError
0x180001d6b  mov     ebx, eax
0x180001d6d  test    eax, eax
0x180001d6f  jle     short loc_180001D7A
0x180001d71  movzx   ebx, ax
0x180001d74  or      ebx, 80070000h
0x180001d7a  mov     rcx, [rsp+0B8h+hMem]; hMem
0x180001d7f  lea     rax, ??_7STBUFF@@6B@; const STBUFF::`vftable'
0x180001d86  mov     [rsp+0B8h+var_88], rax
0x180001d8b  lea     rax, [rsp+0B8h+var_6C]
0x180001d90  cmp     rcx, rax
0x180001d93  jz      short loc_180001D9B
0x180001d95  call    cs:__imp_LocalFree
0x180001d9b  mov     eax, ebx
0x180001d9d  mov     rcx, [rsp+0B8h+var_28]
0x180001da5  xor     rcx, rsp; StackCookie
0x180001da8  call    __security_check_cookie
0x180001dad  mov     rbx, [rsp+0B8h+arg_0]
0x180001db5  add     rsp, 0A0h
0x180001dbc  pop     rdi
0x180001dbd  pop     rsi
0x180001dbe  pop     rbp
0x180001dbf  retn
```
