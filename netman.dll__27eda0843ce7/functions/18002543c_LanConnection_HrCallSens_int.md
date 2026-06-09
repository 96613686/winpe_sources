# LanConnection::HrCallSens(int)

- ea: `0x18002543c`
- end: `0x1800255af`
- name: `?HrCallSens@LanConnection@@AEAAJH@Z`
- size: `371`
- prototype: `__int64 __fastcall(LanConnection *__hidden this, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x1800255b8`

## callees

- `0x180001710`
- `0x18000538c`
- `0x180019200`
- `0x18001e014`
- `0x18002543c`
- `0x18003060c`
- `0x180036010`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x18002549d`
- `KERNEL32!FreeLibrary` at `0x18002555f`
- `KERNEL32!FreeLibrary` at `0x18002549d`
- `KERNEL32!FreeLibrary` at `0x18002555f`
- `KERNEL32!LoadLibraryExW` at `0x180025469`
- `KERNEL32!LoadLibraryExW` at `0x180025469`
- `KERNEL32!GetProcAddress` at `0x180025485`
- `KERNEL32!GetProcAddress` at `0x180025485`

## string_xrefs

- `0x18002545f`: `sens.dll`

## pseudocode

```c
__int64 __fastcall LanConnection::HrCallSens(LanConnection *this, int a2)
{
  HMODULE Library; // rax
  FARPROC ProcAddress; // rsi
  HMODULE v6; // rdi
  signed int Win32Error; // ebx
  const char *v8; // r9
  signed int v9; // eax
  __int64 v11; // [rsp+20h] [rbp-58h] BYREF
  LanConnection *v12; // [rsp+28h] [rbp-50h]

  Library = LoadLibraryExW(L"sens.dll", 0, 0);
  ProcAddress = 0;
  v6 = Library;
  if ( Library )
  {
    Win32Error = 0;
    ProcAddress = GetProcAddress(Library, "SensNotifyNetconEvent");
    if ( !ProcAddress )
    {
      Win32Error = HrFromLastWin32Error();
      FreeLibrary(v6);
    }
  }
  else
  {
    Win32Error = HrFromLastWin32Error();
  }
  if ( Win32Error < 0 )
    goto LABEL_20;
  v12 = this;
  v11 = a2 != 0 ? 32 : 64;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    v8 = "connect";
    if ( !a2 )
      v8 = "disconnect";
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_c391b5a9ef0e35e0488fc434df876d07_Traceguids, v8, v11, v12);
  }
  v9 = ((__int64 (__fastcall *)(__int64 *))ProcAddress)(&v11);
  if ( v9 )
  {
    Win32Error = v9 > 0 ? (unsigned __int16)v9 | 0x80070000 : v9;
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_c391b5a9ef0e35e0488fc434df876d07_Traceguids);
  }
  FreeLibrary(v6);
  if ( Win32Error < 0 )
  {
LABEL_20:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        21,
        &WPP_c391b5a9ef0e35e0488fc434df876d07_Traceguids,
        (unsigned int)Win32Error);
  }
  return (unsigned int)Win32Error;
}

```

## disassembly

```asm
0x18002543c  push    rbx
0x18002543e  push    rbp
0x18002543f  push    rsi
0x180025440  push    rdi
0x180025441  push    r14
0x180025443  push    r15
0x180025445  sub     rsp, 48h
0x180025449  mov     rax, cs:__security_cookie
0x180025450  xor     rax, rsp
0x180025453  mov     [rsp+78h+var_48], rax
0x180025458  mov     ebp, edx
0x18002545a  mov     r14, rcx
0x18002545d  xor     edx, edx; hFile
0x18002545f  lea     rcx, aSensDll; "sens.dll"
0x180025466  xor     r8d, r8d; dwFlags
0x180025469  call    cs:__imp_LoadLibraryExW
0x18002546f  xor     esi, esi
0x180025471  mov     rdi, rax
0x180025474  test    rax, rax
0x180025477  jz      short loc_1800254A5
0x180025479  lea     rdx, aSensnotifynetc; "SensNotifyNetconEvent"
0x180025480  mov     rcx, rax; hModule
0x180025483  xor     ebx, ebx
0x180025485  call    cs:__imp_GetProcAddress
0x18002548b  mov     rsi, rax
0x18002548e  test    rax, rax
0x180025491  jnz     short loc_1800254AC
0x180025493  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x180025498  mov     rcx, rdi; hLibModule
0x18002549b  mov     ebx, eax
0x18002549d  call    cs:__imp_FreeLibrary
0x1800254a3  jmp     short loc_1800254AC
0x1800254a5  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x1800254aa  mov     ebx, eax
0x1800254ac  lea     r15, WPP_GLOBAL_Control
0x1800254b3  test    ebx, ebx
0x1800254b5  js      loc_180025569
0x1800254bb  mov     eax, ebp
0x1800254bd  mov     [rsp+78h+var_54], 0
0x1800254c5  neg     eax
0x1800254c7  mov     [rsp+78h+var_50], r14
0x1800254cc  sbb     ecx, ecx
0x1800254ce  and     ecx, 0FFFFFFE0h
0x1800254d1  add     ecx, 40h ; '@'
0x1800254d4  mov     [rsp+78h+var_58], ecx
0x1800254d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800254df  cmp     rcx, r15
0x1800254e2  jz      short loc_180025513
0x1800254e4  test    byte ptr [rcx+1Ch], 8
0x1800254e8  jz      short loc_180025513
0x1800254ea  mov     rcx, [rcx+10h]
0x1800254ee  lea     rax, aDisconnect; "disconnect"
0x1800254f5  test    ebp, ebp
0x1800254f7  lea     r9, aConnect; "connect"
0x1800254fe  mov     edx, 13h
0x180025503  lea     r8, WPP_c391b5a9ef0e35e0488fc434df876d07_Traceguids
0x18002550a  cmovz   r9, rax
0x18002550e  call    WPP_SF_s
0x180025513  lea     rcx, [rsp+78h+var_58]
0x180025518  mov     rax, rsi
0x18002551b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025520  test    eax, eax
0x180025522  jz      short loc_180025535
0x180025524  jg      short loc_18002552A
0x180025526  mov     ebx, eax
0x180025528  jmp     short loc_18002555C
0x18002552a  movzx   ebx, ax
0x18002552d  or      ebx, 80070000h
0x180025533  jmp     short loc_18002555C
0x180025535  mov     rcx, cs:WPP_GLOBAL_Control
0x18002553c  cmp     rcx, r15
0x18002553f  jz      short loc_18002555C
0x180025541  test    byte ptr [rcx+1Ch], 8
0x180025545  jz      short loc_18002555C
0x180025547  mov     rcx, [rcx+10h]
0x18002554b  lea     r8, WPP_c391b5a9ef0e35e0488fc434df876d07_Traceguids
0x180025552  mov     edx, 14h
0x180025557  call    WPP_SF_
0x18002555c  mov     rcx, rdi; hLibModule
0x18002555f  call    cs:__imp_FreeLibrary
0x180025565  test    ebx, ebx
0x180025567  jns     short loc_180025593
0x180025569  mov     rcx, cs:WPP_GLOBAL_Control
0x180025570  cmp     rcx, r15
0x180025573  jz      short loc_180025593
0x180025575  test    byte ptr [rcx+1Ch], 1
0x180025579  jz      short loc_180025593
0x18002557b  mov     rcx, [rcx+10h]
0x18002557f  lea     r8, WPP_c391b5a9ef0e35e0488fc434df876d07_Traceguids
0x180025586  mov     edx, 15h
0x18002558b  mov     r9d, ebx
0x18002558e  call    WPP_SF_d
0x180025593  mov     eax, ebx
0x180025595  mov     rcx, [rsp+78h+var_48]
0x18002559a  xor     rcx, rsp; StackCookie
0x18002559d  call    __security_check_cookie
0x1800255a2  add     rsp, 48h
0x1800255a6  pop     r15
0x1800255a8  pop     r14
0x1800255aa  pop     rdi
0x1800255ab  pop     rsi
0x1800255ac  pop     rbp
0x1800255ad  pop     rbx
0x1800255ae  retn
```
