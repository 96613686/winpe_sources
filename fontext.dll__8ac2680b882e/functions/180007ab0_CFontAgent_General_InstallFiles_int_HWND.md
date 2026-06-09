# CFontAgent_General::InstallFiles(int,HWND__ *)

- ea: `0x180007ab0`
- end: `0x180007b71`
- name: `?InstallFiles@CFontAgent_General@@UEAAJHPEAUHWND__@@@Z`
- size: `193`
- prototype: `int __fastcall(CFontAgent_General *this, int, HWND)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, service_task, installer_update`

## callees

- `0x180006624`
- `0x180007ab0`
- `0x1800138c8`
- `0x180013a38`
- `0x18003104a`
- `0x180031070`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007b3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007b3e`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x180007b20`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x180007b20`

## pseudocode

```c
int __fastcall CFontAgent_General::InstallFiles(CFontAgent_General *this, int a2, HWND a3)
{
  unsigned __int16 *v5; // rbx
  unsigned int v6; // r9d
  int result; // eax
  unsigned int v8; // edx
  WCHAR NewFileName[264]; // [rsp+20h] [rbp-228h] BYREF

  memset_0(NewFileName, 0, 0x208u);
  v5 = (unsigned __int16 *)((char *)this + 840);
  result = PathAppendFileToFontsDirectory(a2, NewFileName, v5, v6);
  if ( result >= 0 )
  {
    result = PathMakeFilenameUnique(NewFileName, v8, -1);
    if ( result >= 0 )
    {
      if ( CopyFileW(v5, NewFileName, 1) )
      {
        return StringCchCopyW(v5, 0x104u, NewFileName);
      }
      else
      {
        result = GetLastError();
        if ( result > 0 )
          return (unsigned __int16)result | 0x80070000;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180007ab0  mov     [rsp+arg_10], rbx
0x180007ab5  push    rdi
0x180007ab6  sub     rsp, 240h
0x180007abd  mov     rax, cs:__security_cookie
0x180007ac4  xor     rax, rsp
0x180007ac7  mov     [rsp+248h+var_18], rax
0x180007acf  mov     edi, edx
0x180007ad1  mov     rbx, rcx
0x180007ad4  xor     edx, edx; Val
0x180007ad6  lea     rcx, [rsp+248h+NewFileName]; void *
0x180007adb  mov     r8d, 208h; Size
0x180007ae1  call    memset_0
0x180007ae6  add     rbx, 348h
0x180007aed  lea     rdx, [rsp+248h+NewFileName]; unsigned __int16 *
0x180007af2  mov     r8, rbx; unsigned __int16 *
0x180007af5  mov     ecx, edi; int
0x180007af7  call    ?PathAppendFileToFontsDirectory@@YAJHPEAGPEBGI@Z; PathAppendFileToFontsDirectory(int,ushort *,ushort const *,uint)
0x180007afc  test    eax, eax
0x180007afe  js      short loc_180007B50
0x180007b00  or      r8d, 0FFFFFFFFh; int
0x180007b04  lea     rcx, [rsp+248h+NewFileName]; unsigned __int16 *
0x180007b09  call    ?PathMakeFilenameUnique@@YAJPEAGIH@Z; PathMakeFilenameUnique(ushort *,uint,int)
0x180007b0e  test    eax, eax
0x180007b10  js      short loc_180007B50
0x180007b12  mov     r8d, 1; bFailIfExists
0x180007b18  lea     rdx, [rsp+248h+NewFileName]; lpNewFileName
0x180007b1d  mov     rcx, rbx; lpExistingFileName
0x180007b20  call    cs:__imp_CopyFileW
0x180007b26  test    eax, eax
0x180007b28  jz      short loc_180007B3E
0x180007b2a  lea     r8, [rsp+248h+NewFileName]; unsigned __int16 *
0x180007b2f  mov     edx, 104h; unsigned __int64
0x180007b34  mov     rcx, rbx; unsigned __int16 *
0x180007b37  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180007b3c  jmp     short loc_180007B50
0x180007b3e  call    cs:__imp_GetLastError
0x180007b44  test    eax, eax
0x180007b46  jle     short loc_180007B50
0x180007b48  movzx   eax, ax
0x180007b4b  or      eax, 80070000h
0x180007b50  mov     rcx, [rsp+248h+var_18]
0x180007b58  xor     rcx, rsp; StackCookie
0x180007b5b  call    __security_check_cookie
0x180007b60  mov     rbx, [rsp+248h+arg_10]
0x180007b68  add     rsp, 240h
0x180007b6f  pop     rdi
0x180007b70  retn
```
