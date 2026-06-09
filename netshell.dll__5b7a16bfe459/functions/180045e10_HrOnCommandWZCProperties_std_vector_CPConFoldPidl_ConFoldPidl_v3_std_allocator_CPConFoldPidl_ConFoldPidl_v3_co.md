# HrOnCommandWZCProperties(std::vector<CPConFoldPidl<ConFoldPidl_v3>,std::allocator<CPConFoldPidl<ConFoldPidl_v3>>> const &,HWND__ *,IShellFolder *)

- ea: `0x180045e10`
- end: `0x180045fef`
- name: `?HrOnCommandWZCProperties@@YAJAEBV?$vector@V?$CPConFoldPidl@VConFoldPidl_v3@@@@V?$allocator@V?$CPConFoldPidl@VConFoldPidl_v3@@@@@std@@@std@@PEAUHWND__@@PEAUIShellFolder@@@Z`
- size: `479`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180046000`

## callees

- `0x180007de0`
- `0x180018d74`
- `0x18001bc10`
- `0x18001d580`
- `0x18001e1e0`
- `0x180034ba0`
- `0x180040a5c`
- `0x180045e10`
- `0x180049e0c`
- `0x18004bf00`
- `0x18004c388`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180045eb6`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180045eb6`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180045f6d`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180045f6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045f80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045f9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045f80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045f9b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180045ebf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180045ebf`
- `ole32!StringFromGUID2` at `0x180045f5b`
- `ole32!StringFromGUID2` at `0x180045f5b`

## pseudocode

```c
__int64 __fastcall HrOnCommandWZCProperties(__int64 *a1, HWND a2)
{
  __int64 v2; // rsi
  HANDLE MutexW; // rdi
  int v7; // ebx
  unsigned int v8; // r9d
  __int64 v9; // rdx
  int Win32Error; // eax
  struct IUnknown *v11; // [rsp+30h] [rbp-88h] BYREF
  OLECHAR sz[40]; // [rsp+40h] [rbp-78h] BYREF

  v2 = *a1;
  v11 = 0;
  if ( v2 == a1[1] )
    return 0;
  MutexW = 0;
  if ( !*(_QWORD *)v2 )
  {
    v7 = -2147024809;
LABEL_25:
    v8 = 1100;
    goto LABEL_9;
  }
  if ( (((*(_DWORD *)(*(_QWORD *)v2 + 48LL) - 3) & 0xFFFFFFFB) != 0 || (unsigned int)FHasPermission(0xEu))
    && (!(unsigned int)IsMediaRASType((enum tagNETCON_MEDIATYPE)*(_DWORD *)(*(_QWORD *)v2 + 48LL))
     || (unsigned int)FHasPermission((*(_DWORD *)(v9 + 44) & 1u) + 15) == 1) )
  {
    v7 = HrNetConFromPidl(*a1, &v11, 1);
    if ( v7 >= 0 )
    {
      SetLUAParent(v11, a2);
      StringFromGUID2((const GUID *const)(*(_QWORD *)v2 + 28LL), sz, 39);
      MutexW = CreateMutexW(0, 1, sz);
      if ( !MutexW || GetLastError() == 183 )
      {
        if ( GetLastError() == 183 )
        {
          ActivateDialog(0, v11);
          goto LABEL_10;
        }
        Win32Error = HrFromLastWin32Error();
      }
      else
      {
        Win32Error = HrRaiseConnectionPropertiesInternal(0, 1u, *a1);
      }
      v7 = Win32Error;
      if ( Win32Error >= 0 )
        goto LABEL_10;
    }
    if ( v7 != -2147024891 )
    {
      if ( v7 == -2147024882 )
      {
        v8 = 1101;
        goto LABEL_9;
      }
      goto LABEL_25;
    }
  }
  else
  {
    v7 = -2147024891;
  }
  v8 = 1096;
LABEL_9:
  NcMsgBox(hInst, a2, 0x424u, v8, 0x30u);
LABEL_10:
  if ( MutexW )
  {
    ReleaseMutex(MutexW);
    CloseHandle(MutexW);
  }
  ReleaseObj(v11);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180045e10  mov     [rsp+arg_10], rbx
0x180045e15  mov     [rsp+arg_18], rbp
0x180045e1a  push    rsi
0x180045e1b  push    rdi
0x180045e1c  push    r14
0x180045e1e  sub     rsp, 0A0h
0x180045e25  mov     rax, cs:__security_cookie
0x180045e2c  xor     rax, rsp
0x180045e2f  mov     [rsp+0B8h+var_28], rax
0x180045e37  mov     rsi, [rcx]
0x180045e3a  mov     rbp, rdx
0x180045e3d  mov     r14, rcx
0x180045e40  mov     [rsp+0B8h+var_88], 0
0x180045e49  cmp     rsi, [rcx+8]
0x180045e4d  jnz     short loc_180045E53
0x180045e4f  xor     eax, eax
0x180045e51  jmp     short loc_180045ED1
0x180045e53  mov     rax, [rsi]
0x180045e56  xor     edi, edi
0x180045e58  test    rax, rax
0x180045e5b  jnz     short loc_180045E67
0x180045e5d  mov     ebx, 80070057h
0x180045e62  jmp     loc_180045FD9
0x180045e67  mov     eax, [rax+30h]
0x180045e6a  sub     eax, 3
0x180045e6d  test    eax, 0FFFFFFFBh
0x180045e72  jnz     loc_180045EF9
0x180045e78  mov     ecx, 0Eh; unsigned int
0x180045e7d  call    ?FHasPermission@@YAHK@Z; FHasPermission(ulong)
0x180045e82  test    eax, eax
0x180045e84  jnz     short loc_180045EF9
0x180045e86  mov     ebx, 80070005h
0x180045e8b  mov     r9d, 448h; unsigned int
0x180045e91  mov     rcx, cs:hInst; hModule
0x180045e98  mov     r8d, 424h; unsigned int
0x180045e9e  mov     rdx, rbp; hWnd
0x180045ea1  mov     [rsp+0B8h+uType], 30h ; '0'; uType
0x180045ea9  call    ?NcMsgBox@@YAHPEAUHINSTANCE__@@PEAUHWND__@@IIIZZ; NcMsgBox(HINSTANCE__ *,HWND__ *,uint,uint,uint,...)
0x180045eae  test    rdi, rdi
0x180045eb1  jz      short loc_180045EC5
0x180045eb3  mov     rcx, rdi; hMutex
0x180045eb6  call    cs:__imp_ReleaseMutex
0x180045ebc  mov     rcx, rdi; hObject
0x180045ebf  call    cs:__imp_CloseHandle
0x180045ec5  mov     rcx, [rsp+0B8h+var_88]; struct IUnknown *
0x180045eca  call    ?ReleaseObj@@YAKPEAUIUnknown@@@Z; ReleaseObj(IUnknown *)
0x180045ecf  mov     eax, ebx
0x180045ed1  mov     rcx, [rsp+0B8h+var_28]
0x180045ed9  xor     rcx, rsp; StackCookie
0x180045edc  call    __security_check_cookie
0x180045ee1  lea     r11, [rsp+0B8h+var_18]
0x180045ee9  mov     rbx, [r11+30h]
0x180045eed  mov     rbp, [r11+38h]
0x180045ef1  mov     rsp, r11
0x180045ef4  pop     r14
0x180045ef6  pop     rdi
0x180045ef7  pop     rsi
0x180045ef8  retn
0x180045ef9  mov     rdx, [rsi]
0x180045efc  mov     ecx, [rdx+30h]; enum tagNETCON_MEDIATYPE
0x180045eff  call    ?IsMediaRASType@@YAHW4tagNETCON_MEDIATYPE@@@Z; IsMediaRASType(tagNETCON_MEDIATYPE)
0x180045f04  test    eax, eax
0x180045f06  jz      short loc_180045F1F
0x180045f08  mov     ecx, [rdx+2Ch]
0x180045f0b  and     ecx, 1
0x180045f0e  add     ecx, 0Fh; unsigned int
0x180045f11  call    ?FHasPermission@@YAHK@Z; FHasPermission(ulong)
0x180045f16  cmp     eax, 1
0x180045f19  jnz     loc_180045E86
0x180045f1f  mov     rcx, [r14]
0x180045f22  lea     rdx, [rsp+0B8h+var_88]
0x180045f27  mov     r8d, 1
0x180045f2d  call    ?HrNetConFromPidl@@YAJAEBV?$CPConFoldPidl@VConFoldPidl_v3@@@@PEAPEAUINetConnection@@H@Z; HrNetConFromPidl(CPConFoldPidl<ConFoldPidl_v3> const &,INetConnection * *,int)
0x180045f32  mov     ebx, eax
0x180045f34  test    eax, eax
0x180045f36  js      loc_180045FC5
0x180045f3c  mov     rcx, [rsp+0B8h+var_88]; struct IUnknown *
0x180045f41  mov     rdx, rbp; HWND
0x180045f44  call    ?SetLUAParent@@YAXPEAUIUnknown@@PEAUHWND__@@@Z; SetLUAParent(IUnknown *,HWND__ *)
0x180045f49  mov     rcx, [rsi]
0x180045f4c  lea     rdx, [rsp+0B8h+sz]; lpsz
0x180045f51  add     rcx, 1Ch; rguid
0x180045f55  mov     r8d, 27h ; '''; cchMax
0x180045f5b  call    cs:__imp_StringFromGUID2
0x180045f61  lea     r8, [rsp+0B8h+sz]; lpName
0x180045f66  mov     edx, 1; bInitialOwner
0x180045f6b  xor     ecx, ecx; lpMutexAttributes
0x180045f6d  call    cs:__imp_CreateMutexW
0x180045f73  mov     rdi, rax
0x180045f76  mov     esi, 0B7h
0x180045f7b  test    rax, rax
0x180045f7e  jz      short loc_180045F9B
0x180045f80  call    cs:__imp_GetLastError
0x180045f86  cmp     eax, esi
0x180045f88  jz      short loc_180045F9B
0x180045f8a  mov     r8, [r14]
0x180045f8d  mov     edx, 1
0x180045f92  xor     ecx, ecx; HWND
0x180045f94  call    ?HrRaiseConnectionPropertiesInternal@@YAJPEAUHWND__@@IAEBV?$CPConFoldPidl@VConFoldPidl_v3@@@@@Z; HrRaiseConnectionPropertiesInternal(HWND__ *,uint,CPConFoldPidl<ConFoldPidl_v3> const &)
0x180045f99  jmp     short loc_180045FBB
0x180045f9b  call    cs:__imp_GetLastError
0x180045fa1  cmp     eax, esi
0x180045fa3  jnz     short loc_180045FB6
0x180045fa5  mov     rdx, [rsp+0B8h+var_88]
0x180045faa  xor     ecx, ecx
0x180045fac  call    ?ActivateDialog@@YAXW4DIALOG_TYPE@@PEAUINetConnection@@@Z; ActivateDialog(DIALOG_TYPE,INetConnection *)
0x180045fb1  jmp     loc_180045EAE
0x180045fb6  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x180045fbb  mov     ebx, eax
0x180045fbd  test    eax, eax
0x180045fbf  jns     loc_180045EAE
0x180045fc5  cmp     ebx, 80070005h
0x180045fcb  jz      loc_180045E8B
0x180045fd1  cmp     ebx, 8007000Eh
0x180045fd7  jz      short loc_180045FE4
0x180045fd9  mov     r9d, 44Ch
0x180045fdf  jmp     loc_180045E91
0x180045fe4  mov     r9d, 44Dh
0x180045fea  jmp     loc_180045E91
```
