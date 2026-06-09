# GetMSWsockBuildVersion(ushort *,ushort *)

- ea: `0x100434b2c`
- end: `0x100434d6e`
- name: `?GetMSWsockBuildVersion@@YAKPEAG0@Z`
- size: `578`
- prototype: `unsigned int __fastcall(unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x100434218`

## callees

- `0x100434a28`
- `0x100434b2c`
- `0x100546aa8`
- `0x100546e27`
- `0x100546e33`
- `0x100546e3f`
- `0x100548210`
- `0x1005495d0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x100434b95`
- `KERNEL32!GetLastError` at `0x100434c67`
- `KERNEL32!GetLastError` at `0x100434b95`
- `KERNEL32!GetLastError` at `0x100434c67`

## string_xrefs

- `0x100434b6a`: `mswsock.dll`

## pseudocode

```c
__int64 __fastcall GetMSWsockBuildVersion(unsigned __int16 *a1, unsigned __int16 *a2)
{
  DWORD FullPathToSystemDLL; // ebx
  DWORD FileVersionInfoSizeW_0; // eax
  DWORD v6; // ebx
  void *v7; // rax
  const void *v8; // rdi
  _WORD *v9; // rcx
  DWORD dwHandle; // [rsp+30h] [rbp-248h] BYREF
  unsigned int puLen; // [rsp+34h] [rbp-244h] BYREF
  LPVOID lpBuffer; // [rsp+38h] [rbp-240h] BYREF
  WCHAR tstrFilename[264]; // [rsp+40h] [rbp-238h] BYREF

  dwHandle = 0;
  lpBuffer = 0;
  FullPathToSystemDLL = GetFullPathToSystemDLL("mswsock.dll", tstrFilename, 0x104u);
  if ( !FullPathToSystemDLL )
  {
    FileVersionInfoSizeW_0 = GetFileVersionInfoSizeW_0(tstrFilename, &dwHandle);
    v6 = FileVersionInfoSizeW_0;
    if ( FileVersionInfoSizeW_0 )
    {
      v7 = (void *)(*(__int64 (__fastcall **)(struct ISOSHost_MemObj *, _QWORD))(*(_QWORD *)gpmo + 112LL))(
                     gpmo,
                     FileVersionInfoSizeW_0);
      v8 = v7;
      if ( v7 )
      {
        if ( GetFileVersionInfoW_0(tstrFilename, dwHandle, v6, v7) )
        {
          if ( VerQueryValueW_0(v8, L"\\", &lpBuffer, &puLen) && puLen == 52 )
          {
            v9 = lpBuffer;
            FullPathToSystemDLL = 0;
            *a1 = *((_WORD *)lpBuffer + 7);
            *a2 = v9[6];
          }
          else
          {
            FullPathToSystemDLL = -1;
            if ( (bidGblFlags & 2) != 0 && off_1005E5648[0] && bidID != -1 )
              ((void (__fastcall *)(__int64, _QWORD, __int64, wchar_t *, _QWORD))off_1005D39E0)(
                bidID,
                0,
                288768,
                off_1005E5648[0],
                0);
          }
        }
        else
        {
          FullPathToSystemDLL = GetLastError();
          if ( (bidGblFlags & 2) != 0 && off_1005E5640[0] )
            bidTraceW(0, 276480, off_1005E5640[0], FullPathToSystemDLL);
        }
        ((void (__fastcall *)(struct IMalloc *, const void *))g_pMO->lpVtbl[1].DidAlloc)(g_pMO, v8);
      }
      else
      {
        FullPathToSystemDLL = 14;
        if ( (bidGblFlags & 2) != 0 && off_1005E5638[0] && bidID != -1 )
          ((void (__fastcall *)(__int64, _QWORD, __int64, wchar_t *, _QWORD))off_1005D39E0)(
            bidID,
            0,
            269312,
            off_1005E5638[0],
            0);
      }
    }
    else
    {
      FullPathToSystemDLL = GetLastError();
      if ( (bidGblFlags & 2) != 0 && off_1005E5630[0] )
        bidTraceW(0, 260096, off_1005E5630[0], FullPathToSystemDLL);
    }
  }
  return FullPathToSystemDLL;
}

```

## disassembly

```asm
0x100434b2c  mov     [rsp+arg_10], rbx
0x100434b31  push    rsi
0x100434b32  push    rdi
0x100434b33  push    r14
0x100434b35  sub     rsp, 260h
0x100434b3c  mov     rax, cs:__security_cookie
0x100434b43  xor     rax, rsp
0x100434b46  mov     [rsp+278h+var_28], rax
0x100434b4e  and     [rsp+278h+dwHandle], 0
0x100434b53  mov     r14, rdx
0x100434b56  and     [rsp+278h+lpBuffer], 0
0x100434b5c  lea     rdx, [rsp+278h+tstrFilename]; unsigned __int16 *
0x100434b61  mov     rsi, rcx
0x100434b64  mov     r8d, 104h; unsigned int
0x100434b6a  lea     rcx, aMswsockDll; "mswsock.dll"
0x100434b71  call    ?GetFullPathToSystemDLL@@YAKPEBDPEAGK@Z; GetFullPathToSystemDLL(char const *,ushort *,ulong)
0x100434b76  mov     ebx, eax
0x100434b78  test    eax, eax
0x100434b7a  jnz     loc_100434D48
0x100434b80  lea     rdx, [rsp+278h+dwHandle]; lpdwHandle
0x100434b85  lea     rcx, [rsp+278h+tstrFilename]; lptstrFilename
0x100434b8a  call    GetFileVersionInfoSizeW_0
0x100434b8f  mov     ebx, eax
0x100434b91  test    eax, eax
0x100434b93  jnz     short loc_100434BD5
0x100434b95  call    cs:__imp_GetLastError
0x100434b9b  test    byte ptr cs:_bidGblFlags, 2
0x100434ba2  mov     ebx, eax
0x100434ba4  jz      loc_100434D48
0x100434baa  mov     rax, cs:off_1005E5630; "<GetMSWsockBuildVersion|ERR|SNI> GetFil"...
0x100434bb1  test    rax, rax
0x100434bb4  jz      loc_100434D48
0x100434bba  mov     r8, cs:off_1005E5630; "<GetMSWsockBuildVersion|ERR|SNI> GetFil"...
0x100434bc1  mov     r9d, ebx
0x100434bc4  mov     edx, 3F800h
0x100434bc9  xor     ecx, ecx
0x100434bcb  call    _bidTraceW
0x100434bd0  jmp     loc_100434D48
0x100434bd5  mov     rcx, cs:?gpmo@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * gpmo
0x100434bdc  mov     rdx, rbx
0x100434bdf  mov     rax, [rcx]
0x100434be2  mov     rax, [rax+70h]
0x100434be6  call    cs:__guard_dispatch_icall_fptr
0x100434bec  mov     rdi, rax
0x100434bef  test    rax, rax
0x100434bf2  jnz     short loc_100434C4F
0x100434bf4  test    byte ptr cs:_bidGblFlags, 2
0x100434bfb  lea     ebx, [rax+0Eh]
0x100434bfe  jz      loc_100434D48
0x100434c04  mov     rax, cs:off_1005E5638; "<GetMSWsockBuildVersion|ERR|SNI> Memory"...
0x100434c0b  test    rax, rax
0x100434c0e  jz      loc_100434D48
0x100434c14  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x100434c1c  jz      loc_100434D48
0x100434c22  mov     r9, cs:off_1005E5638; "<GetMSWsockBuildVersion|ERR|SNI> Memory"...
0x100434c29  xor     edx, edx
0x100434c2b  mov     rcx, cs:_bidID
0x100434c32  mov     r8d, 41C00h
0x100434c38  mov     rax, cs:off_1005D39E0
0x100434c3f  and     [rsp+278h+var_258], rdi
0x100434c44  call    cs:__guard_dispatch_icall_fptr
0x100434c4a  jmp     loc_100434D48
0x100434c4f  mov     edx, [rsp+278h+dwHandle]; dwHandle
0x100434c53  lea     rcx, [rsp+278h+tstrFilename]; lptstrFilename
0x100434c58  mov     r9, rdi; lpData
0x100434c5b  mov     r8d, ebx; dwLen
0x100434c5e  call    GetFileVersionInfoW_0
0x100434c63  test    eax, eax
0x100434c65  jnz     short loc_100434CA7
0x100434c67  call    cs:__imp_GetLastError
0x100434c6d  test    byte ptr cs:_bidGblFlags, 2
0x100434c74  mov     ebx, eax
0x100434c76  jz      loc_100434D2E
0x100434c7c  mov     rax, cs:off_1005E5640; "<GetMSWsockBuildVersion|ERR|SNI> GetFil"...
0x100434c83  test    rax, rax
0x100434c86  jz      loc_100434D2E
0x100434c8c  mov     r8, cs:off_1005E5640; "<GetMSWsockBuildVersion|ERR|SNI> GetFil"...
0x100434c93  mov     r9d, ebx
0x100434c96  mov     edx, 43800h
0x100434c9b  xor     ecx, ecx
0x100434c9d  call    _bidTraceW
0x100434ca2  jmp     loc_100434D2E
0x100434ca7  lea     r9, [rsp+278h+puLen]; puLen
0x100434cac  mov     rcx, rdi; pBlock
0x100434caf  lea     r8, [rsp+278h+lpBuffer]; lplpBuffer
0x100434cb4  lea     rdx, SubBlock; "\\"
0x100434cbb  call    VerQueryValueW_0
0x100434cc0  test    eax, eax
0x100434cc2  jz      short loc_100434CE3
0x100434cc4  cmp     [rsp+278h+puLen], 34h ; '4'
0x100434cc9  jnz     short loc_100434CE3
0x100434ccb  mov     rcx, [rsp+278h+lpBuffer]
0x100434cd0  xor     ebx, ebx
0x100434cd2  movzx   eax, word ptr [rcx+0Eh]
0x100434cd6  mov     [rsi], ax
0x100434cd9  movzx   eax, word ptr [rcx+0Ch]
0x100434cdd  mov     [r14], ax
0x100434ce1  jmp     short loc_100434D2E
0x100434ce3  or      ebx, 0FFFFFFFFh
0x100434ce6  test    byte ptr cs:_bidGblFlags, 2
0x100434ced  jz      short loc_100434D2E
0x100434cef  mov     rax, cs:off_1005E5648; "<GetMSWsockBuildVersion|ERR|SNI> VerQue"...
0x100434cf6  test    rax, rax
0x100434cf9  jz      short loc_100434D2E
0x100434cfb  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x100434d03  jz      short loc_100434D2E
0x100434d05  mov     r9, cs:off_1005E5648; "<GetMSWsockBuildVersion|ERR|SNI> VerQue"...
0x100434d0c  xor     edx, edx
0x100434d0e  mov     rcx, cs:_bidID
0x100434d15  mov     r8d, 46800h
0x100434d1b  mov     rax, cs:off_1005D39E0
0x100434d22  and     [rsp+278h+var_258], 0
0x100434d28  call    cs:__guard_dispatch_icall_fptr
0x100434d2e  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x100434d35  mov     rdx, rdi
0x100434d38  mov     rax, [rcx]
0x100434d3b  mov     rax, [rax+80h]
0x100434d42  call    cs:__guard_dispatch_icall_fptr
0x100434d48  mov     eax, ebx
0x100434d4a  mov     rcx, [rsp+278h+var_28]
0x100434d52  xor     rcx, rsp; StackCookie
0x100434d55  call    __security_check_cookie
0x100434d5a  mov     rbx, [rsp+278h+arg_10]
0x100434d62  add     rsp, 260h
0x100434d69  pop     r14
0x100434d6b  pop     rdi
0x100434d6c  pop     rsi
0x100434d6d  retn
```
