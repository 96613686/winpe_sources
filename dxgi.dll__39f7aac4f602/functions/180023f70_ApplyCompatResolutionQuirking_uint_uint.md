# ApplyCompatResolutionQuirking(uint *,uint *)

- ea: `0x180023f70`
- end: `0x1800241c7`
- name: `?ApplyCompatResolutionQuirking@@YAXPEAI0@Z`
- size: `599`
- prototype: `void __fastcall(unsigned int *, unsigned int *)`
- caller_count: `5`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180023280`
- `0x180023dc8`
- `0x1800375a4`
- `0x18005f760`
- `0x180063198`

## callees

- `0x180023f70`
- `0x180075fa0`
- `0x180076f20`
- `0x18007abd0`
- `0x1800a72b4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002411d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002411d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800240b3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800240b3`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18002412f`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18002412f`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180024027`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180024027`
- `api-ms-win-core-quirks-l1-1-0!QuirkIsEnabled` at `0x180023fed`
- `api-ms-win-core-quirks-l1-1-0!QuirkIsEnabled` at `0x180024184`
- `api-ms-win-core-quirks-l1-1-0!QuirkIsEnabled` at `0x1800241a8`
- `api-ms-win-core-quirks-l1-1-0!QuirkIsEnabled` at `0x180023fed`
- `api-ms-win-core-quirks-l1-1-0!QuirkIsEnabled` at `0x180024184`
- `api-ms-win-core-quirks-l1-1-0!QuirkIsEnabled` at `0x1800241a8`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!EnumDisplaySettingsW` at `0x180024069`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!EnumDisplaySettingsW` at `0x180024069`

## pseudocode

```c
void __fastcall ApplyCompatResolutionQuirking(unsigned int *a1, unsigned int *a2)
{
  WINBOOL fPending; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  DEVMODEW DevMode; // [rsp+40h] [rbp-C0h] BYREF

  if ( (unsigned __int8)IsShell_IsLockedPresent() )
  {
    if ( (_DWORD)qword_180109A08 )
    {
      fPending = 0;
      if ( InitOnceBeginInitialize(&InitOnce, 0, &fPending, 0) )
      {
        if ( fPending )
        {
          byte_18010C260 = 0;
          memset_0(&DevMode, 0, sizeof(DevMode));
          DevMode.dmSize = 220;
          if ( EnumDisplaySettingsW(0, 0xFFFFFFFF, &DevMode) )
          {
            dword_18010C250 = DevMode.dmPelsWidth;
            dword_18010C254 = DevMode.dmPelsHeight;
            hKey = 0;
            if ( !RegOpenKeyExA(HKEY_LOCAL_MACHINE, "Software\\Microsoft\\Shell\\LogicalResolution", 0, 1u, &hKey) )
            {
              if ( RegDWORD(hKey, "Height", &dword_18010C25C)
                && RegDWORD(hKey, "Width", &dword_18010C258)
                && (dword_18010C258 != dword_18010C250 || dword_18010C25C != dword_18010C254) )
              {
                byte_18010C260 = 1;
              }
              RegCloseKey(hKey);
            }
          }
          InitOnceComplete(&InitOnce, 0, 0);
        }
        if ( byte_18010C260 && *a1 == dword_18010C250 && *a2 == dword_18010C254 )
        {
          *a1 = dword_18010C258;
          *a2 = dword_18010C25C;
        }
      }
    }
  }
  if ( *a1 == 1080 && *a2 == 1920 && (unsigned int)QuirkIsEnabled(0x100000) )
    goto LABEL_8;
  if ( *a1 == 540 && *a2 == 960 && (unsigned int)QuirkIsEnabled(1048577) )
  {
    *a1 = 480;
    *a2 = 800;
    return;
  }
  if ( *a1 == 1440 && *a2 == 2560 && (unsigned int)QuirkIsEnabled(1048582) )
  {
LABEL_8:
    *a1 = 720;
    *a2 = 1280;
  }
}

```

## disassembly

```asm
0x180023f70  mov     [rsp-8+arg_10], rbx
0x180023f75  push    rbp
0x180023f76  push    rsi
0x180023f77  push    rdi
0x180023f78  lea     rbp, [rsp-30h]
0x180023f7d  sub     rsp, 130h
0x180023f84  mov     rax, cs:__security_cookie
0x180023f8b  xor     rax, rsp
0x180023f8e  mov     [rbp+40h+var_20], rax
0x180023f92  mov     rdi, rdx
0x180023f95  mov     rbx, rcx
0x180023f98  call    IsShell_IsLockedPresent
0x180023f9d  test    al, al
0x180023f9f  jnz     short loc_180024005
0x180023fa1  cmp     dword ptr [rbx], 438h
0x180023fa7  jz      loc_180024173
0x180023fad  cmp     dword ptr [rbx], 21Ch
0x180023fb3  jz      loc_180024197
0x180023fb9  cmp     dword ptr [rbx], 5A0h
0x180023fbf  jz      short loc_180023FE0
0x180023fc1  mov     rcx, [rbp+40h+var_20]
0x180023fc5  xor     rcx, rsp; StackCookie
0x180023fc8  call    __security_check_cookie
0x180023fcd  mov     rbx, [rsp+140h+arg_10]
0x180023fd5  add     rsp, 130h
0x180023fdc  pop     rdi
0x180023fdd  pop     rsi
0x180023fde  pop     rbp
0x180023fdf  retn
0x180023fe0  cmp     dword ptr [rdi], 0A00h
0x180023fe6  jnz     short loc_180023FC1
0x180023fe8  mov     ecx, 100006h
0x180023fed  call    cs:__imp_QuirkIsEnabled
0x180023ff3  test    eax, eax
0x180023ff5  jz      short loc_180023FC1
0x180023ff7  mov     dword ptr [rbx], 2D0h
0x180023ffd  mov     dword ptr [rdi], 500h
0x180024003  jmp     short loc_180023FC1
0x180024005  cmp     dword ptr cs:qword_180109A08, 0
0x18002400c  jz      short loc_180023FA1
0x18002400e  xor     r9d, r9d; lpContext
0x180024011  mov     [rsp+140h+fPending], 0
0x180024019  lea     r8, [rsp+140h+fPending]; fPending
0x18002401e  xor     edx, edx; dwFlags
0x180024020  lea     rcx, InitOnce; lpInitOnce
0x180024027  call    cs:__imp_InitOnceBeginInitialize
0x18002402d  test    eax, eax
0x18002402f  jz      loc_180023FA1
0x180024035  cmp     [rsp+140h+fPending], 0
0x18002403a  jz      loc_180024135
0x180024040  mov     esi, 0DCh
0x180024045  mov     cs:byte_18010C260, 0
0x18002404c  mov     r8d, esi; Size
0x18002404f  lea     rcx, [rsp+140h+DevMode]; void *
0x180024054  xor     edx, edx; Val
0x180024056  call    memset_0
0x18002405b  lea     r8, [rsp+140h+DevMode]; lpDevMode
0x180024060  mov     [rbp+40h+DevMode.dmSize], si
0x180024064  or      edx, 0FFFFFFFFh; iModeNum
0x180024067  xor     ecx, ecx; lpszDeviceName
0x180024069  call    cs:__imp_EnumDisplaySettingsW
0x18002406f  test    eax, eax
0x180024071  jz      loc_180024123
0x180024077  mov     eax, [rbp+40h+DevMode.dmPelsWidth]
0x18002407a  lea     rdx, SubKey; "Software\\Microsoft\\Shell\\LogicalReso"...
0x180024081  mov     cs:dword_18010C250, eax
0x180024087  mov     r9d, 1; samDesired
0x18002408d  mov     eax, [rbp+40h+DevMode.dmPelsHeight]
0x180024090  xor     r8d, r8d; ulOptions
0x180024093  mov     cs:dword_18010C254, eax
0x180024099  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800240a0  lea     rax, [rsp+140h+hKey]
0x1800240a5  mov     [rsp+140h+hKey], 0
0x1800240ae  mov     [rsp+140h+phkResult], rax; phkResult
0x1800240b3  call    cs:__imp_RegOpenKeyExA
0x1800240b9  test    eax, eax
0x1800240bb  jnz     short loc_180024123
0x1800240bd  mov     rcx, [rsp+140h+hKey]; HKEY
0x1800240c2  lea     r8, dword_18010C25C; unsigned int *
0x1800240c9  lea     rdx, aHeight; "Height"
0x1800240d0  call    ?RegDWORD@@YA_NPEAUHKEY__@@PEBDPEAK@Z; RegDWORD(HKEY__ *,char const *,ulong *)
0x1800240d5  test    al, al
0x1800240d7  jz      short loc_180024118
0x1800240d9  mov     rcx, [rsp+140h+hKey]; HKEY
0x1800240de  lea     r8, dword_18010C258; unsigned int *
0x1800240e5  lea     rdx, aWidth; "Width"
0x1800240ec  call    ?RegDWORD@@YA_NPEAUHKEY__@@PEBDPEAK@Z; RegDWORD(HKEY__ *,char const *,ulong *)
0x1800240f1  test    al, al
0x1800240f3  jz      short loc_180024118
0x1800240f5  mov     eax, cs:dword_18010C250
0x1800240fb  cmp     cs:dword_18010C258, eax
0x180024101  jnz     short loc_180024111
0x180024103  mov     eax, cs:dword_18010C254
0x180024109  cmp     cs:dword_18010C25C, eax
0x18002410f  jz      short loc_180024118
0x180024111  mov     cs:byte_18010C260, 1
0x180024118  mov     rcx, [rsp+140h+hKey]; hKey
0x18002411d  call    cs:__imp_RegCloseKey
0x180024123  xor     r8d, r8d; lpContext
0x180024126  lea     rcx, InitOnce; lpInitOnce
0x18002412d  xor     edx, edx; dwFlags
0x18002412f  call    cs:__imp_InitOnceComplete
0x180024135  cmp     cs:byte_18010C260, 0
0x18002413c  jz      loc_180023FA1
0x180024142  mov     eax, cs:dword_18010C250
0x180024148  cmp     [rbx], eax
0x18002414a  jnz     loc_180023FA1
0x180024150  mov     eax, cs:dword_18010C254
0x180024156  cmp     [rdi], eax
0x180024158  jnz     loc_180023FA1
0x18002415e  mov     eax, cs:dword_18010C258
0x180024164  mov     [rbx], eax
0x180024166  mov     eax, cs:dword_18010C25C
0x18002416c  mov     [rdi], eax
0x18002416e  jmp     loc_180023FA1
0x180024173  cmp     dword ptr [rdi], 780h
0x180024179  jnz     loc_180023FAD
0x18002417f  mov     ecx, 100000h
0x180024184  call    cs:__imp_QuirkIsEnabled
0x18002418a  test    eax, eax
0x18002418c  jnz     loc_180023FF7
0x180024192  jmp     loc_180023FAD
0x180024197  cmp     dword ptr [rdi], 3C0h
0x18002419d  jnz     loc_180023FB9
0x1800241a3  mov     ecx, 100001h
0x1800241a8  call    cs:__imp_QuirkIsEnabled
0x1800241ae  test    eax, eax
0x1800241b0  jz      loc_180023FB9
0x1800241b6  mov     dword ptr [rbx], 1E0h
0x1800241bc  mov     dword ptr [rdi], 320h
0x1800241c2  jmp     loc_180023FC1
```
