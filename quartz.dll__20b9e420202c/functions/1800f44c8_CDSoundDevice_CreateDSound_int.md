# CDSoundDevice::CreateDSound(int)

- ea: `0x1800f44c8`
- end: `0x1800f479c`
- name: `?CreateDSound@CDSoundDevice@@AEAAJH@Z`
- size: `724`
- prototype: `__int64 __fastcall(CDSoundDevice *__hidden this, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180030d80`
- `0x1800f5b30`

## callees

- `0x1800388a0`
- `0x1800f44c8`
- `0x18015e010`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x1800f4520`
- `KERNEL32!LoadLibraryExW` at `0x1800f4520`
- `KERNEL32!GetProcAddress` at `0x1800f4546`
- `KERNEL32!GetProcAddress` at `0x1800f4546`
- `USER32!GetDesktopWindow` at `0x1800f4703`
- `USER32!GetDesktopWindow` at `0x1800f4749`
- `USER32!GetDesktopWindow` at `0x1800f4703`
- `USER32!GetDesktopWindow` at `0x1800f4749`
- `USER32!GetForegroundWindow` at `0x1800f46ef`
- `USER32!GetForegroundWindow` at `0x1800f4735`
- `USER32!GetForegroundWindow` at `0x1800f46ef`
- `USER32!GetForegroundWindow` at `0x1800f4735`
- `ole32!CoCreateInstance` at `0x1800f4599`
- `ole32!CoCreateInstance` at `0x1800f4599`

## string_xrefs

- `0x1800f4513`: `DSOUND.DLL`
- `0x1800f453c`: `DirectSoundCreate`

## pseudocode

```c
__int64 __fastcall CDSoundDevice::CreateDSound(CDSoundDevice *this, int a2)
{
  _QWORD *v2; // rsi
  HMODULE Library; // rax
  FARPROC ProcAddress; // r9
  HRESULT v7; // edi
  __int64 v8; // rax
  int v9; // eax
  __int128 v10; // xmm0
  __int64 result; // rax
  __int64 v12; // rax
  char *v13; // rcx
  int v14; // ecx
  HWND ForegroundWindow; // rdx
  int i; // ebx
  HWND DesktopWindow; // rdx
  __int64 v18; // [rsp+30h] [rbp-50h] BYREF
  LPVOID ppv; // [rsp+38h] [rbp-48h] BYREF
  __int128 v20; // [rsp+40h] [rbp-40h] BYREF
  int *v21; // [rsp+50h] [rbp-30h]
  int v22; // [rsp+58h] [rbp-28h] BYREF
  __int128 v23; // [rsp+5Ch] [rbp-24h]
  int v24; // [rsp+6Ch] [rbp-14h]

  v2 = (_QWORD *)((char *)this + 144);
  if ( *((_QWORD *)this + 18) )
    goto LABEL_24;
  Library = (HMODULE)*((_QWORD *)this + 17);
  if ( !Library )
  {
    Library = LoadLibraryExW(L"DSOUND.DLL", 0, 0x800u);
    *((_QWORD *)this + 17) = Library;
    if ( !Library )
      return 6;
  }
  ProcAddress = GetProcAddress(Library, "DirectSoundCreate");
  if ( !ProcAddress )
    return 6;
  if ( *((_QWORD *)this + 25) )
  {
    ppv = 0;
    v18 = 0;
    v7 = CoCreateInstance(
           &GUID_bcde0395_e52f_467c_8e3d_c4579291692e,
           0,
           1u,
           &GUID_a95664d2_9614_4f35_a746_de8db63617e6,
           &ppv);
    if ( !v7 )
    {
      v8 = *(_QWORD *)ppv;
      if ( *((_DWORD *)this + 52) )
        v9 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, _QWORD, __int64 *))(v8 + 32))(
               ppv,
               *((unsigned int *)this + 54),
               *((unsigned int *)this + 53),
               &v18);
      else
        v9 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, __int64 *))(v8 + 40))(ppv, *((_QWORD *)this + 25), &v18);
      v7 = v9;
      if ( v9 >= 0 )
      {
        v10 = *(_OWORD *)((char *)this + 236);
        v24 = *((_DWORD *)this + 63);
        v22 = 24;
        v20 = 0;
        DWORD2(v20) = 24;
        LOWORD(v20) = 65;
        v21 = &v22;
        v23 = v10;
        v7 = (*(__int64 (__fastcall **)(__int64, GUID *, __int64, __int128 *, _QWORD *))(*(_QWORD *)v18 + 24LL))(
               v18,
               &IID_IDirectSound,
               23,
               &v20,
               v2);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
      }
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    }
    if ( v7 < 0 )
      return (unsigned int)v7;
    goto LABEL_24;
  }
  v12 = *(_QWORD *)((char *)this + 220) - *(_QWORD *)&GUID_00000000_0000_0000_0000_000000000000.Data1;
  if ( !v12 )
    v12 = *(_QWORD *)((char *)this + 228) - *(_QWORD *)GUID_00000000_0000_0000_0000_000000000000.Data4;
  v13 = 0;
  if ( v12 )
    v13 = (char *)this + 220;
  v14 = ((__int64 (__fastcall *)(char *, _QWORD *, _QWORD))ProcAddress)(v13, v2, 0);
  if ( !v14 )
  {
LABEL_24:
    if ( !a2 )
    {
      ForegroundWindow = (HWND)*((_QWORD *)this + 6);
      if ( !ForegroundWindow )
      {
        ForegroundWindow = GetForegroundWindow();
        if ( !ForegroundWindow )
          ForegroundWindow = GetDesktopWindow();
      }
      if ( (*(unsigned int (__fastcall **)(_QWORD, HWND, __int64))(*(_QWORD *)*v2 + 48LL))(*v2, ForegroundWindow, 2)
        && !*((_BYTE *)this + 56) )
      {
        for ( i = 0; i < 10; ++i )
        {
          DesktopWindow = GetForegroundWindow();
          if ( !DesktopWindow )
            DesktopWindow = GetDesktopWindow();
          if ( !(*(unsigned int (__fastcall **)(_QWORD, HWND, __int64))(*(_QWORD *)*v2 + 48LL))(*v2, DesktopWindow, 2) )
            break;
        }
      }
    }
    return 0;
  }
  result = 6;
  if ( v14 == -2005401590 )
    return 4;
  return result;
}

```

## disassembly

```asm
0x1800f44c8  mov     [rsp-18h+arg_8], rbx
0x1800f44cd  mov     [rsp-18h+arg_10], rsi
0x1800f44d2  push    rbp
0x1800f44d3  push    rdi
0x1800f44d4  push    r14
0x1800f44d6  mov     rbp, rsp
0x1800f44d9  sub     rsp, 80h
0x1800f44e0  mov     rax, cs:__security_cookie
0x1800f44e7  xor     rax, rsp
0x1800f44ea  mov     [rbp+var_10], rax
0x1800f44ee  lea     rsi, [rcx+90h]
0x1800f44f5  mov     r14d, edx
0x1800f44f8  cmp     qword ptr [rsi], 0
0x1800f44fc  mov     rbx, rcx
0x1800f44ff  jnz     loc_1800F46DD
0x1800f4505  mov     rax, [rcx+88h]
0x1800f450c  test    rax, rax
0x1800f450f  jnz     short loc_1800F453C
0x1800f4511  xor     edx, edx; hFile
0x1800f4513  lea     rcx, aDsoundDll; "DSOUND.DLL"
0x1800f451a  mov     r8d, 800h; dwFlags
0x1800f4520  call    cs:__imp_LoadLibraryExW
0x1800f4527  nop     dword ptr [rax+rax+00h]
0x1800f452c  mov     [rbx+88h], rax
0x1800f4533  test    rax, rax
0x1800f4536  jz      loc_1800F46D3
0x1800f453c  lea     rdx, aDirectsoundcre; "DirectSoundCreate"
0x1800f4543  mov     rcx, rax; hModule
0x1800f4546  call    cs:__imp_GetProcAddress
0x1800f454d  nop     dword ptr [rax+rax+00h]
0x1800f4552  mov     r9, rax
0x1800f4555  test    rax, rax
0x1800f4558  jz      loc_1800F46D3
0x1800f455e  cmp     qword ptr [rbx+0C8h], 0
0x1800f4566  jz      loc_1800F467D
0x1800f456c  xor     edx, edx; pUnkOuter
0x1800f456e  mov     [rbp+var_48], 0
0x1800f4576  lea     rax, [rbp+var_48]
0x1800f457a  mov     [rbp+var_50], 0
0x1800f4582  lea     r9, _GUID_a95664d2_9614_4f35_a746_de8db63617e6; riid
0x1800f4589  mov     [rsp+80h+ppv], rax; ppv
0x1800f458e  lea     rcx, _GUID_bcde0395_e52f_467c_8e3d_c4579291692e; rclsid
0x1800f4595  lea     r8d, [rdx+1]; dwClsContext
0x1800f4599  call    cs:__imp_CoCreateInstance
0x1800f45a0  nop     dword ptr [rax+rax+00h]
0x1800f45a5  mov     edi, eax
0x1800f45a7  test    eax, eax
0x1800f45a9  jnz     loc_1800F4672
0x1800f45af  mov     rcx, [rbp+var_48]
0x1800f45b3  mov     rax, [rcx]
0x1800f45b6  cmp     [rbx+0D0h], edi
0x1800f45bc  jz      short loc_1800F45DA
0x1800f45be  mov     r8d, [rbx+0D4h]
0x1800f45c5  lea     r9, [rbp+var_50]
0x1800f45c9  mov     edx, [rbx+0D8h]
0x1800f45cf  mov     rax, [rax+20h]
0x1800f45d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f45d8  jmp     short loc_1800F45EE
0x1800f45da  mov     rdx, [rbx+0C8h]
0x1800f45e1  lea     r8, [rbp+var_50]
0x1800f45e5  mov     rax, [rax+28h]
0x1800f45e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f45ee  mov     edi, eax
0x1800f45f0  test    eax, eax
0x1800f45f2  js      short loc_1800F4662
0x1800f45f4  mov     eax, [rbx+0FCh]
0x1800f45fa  lea     r9, [rbp+var_40]
0x1800f45fe  movups  xmm0, xmmword ptr [rbx+0ECh]
0x1800f4605  mov     [rbp+var_14], eax
0x1800f4608  lea     rdx, IID_IDirectSound
0x1800f460f  mov     ecx, 18h
0x1800f4614  mov     [rsp+80h+ppv], rsi
0x1800f4619  mov     [rbp+var_28], ecx
0x1800f461c  xorps   xmm1, xmm1
0x1800f461f  movups  [rbp+var_40], xmm1
0x1800f4623  mov     dword ptr [rbp+var_40+8], ecx
0x1800f4626  mov     r8d, 17h
0x1800f462c  lea     eax, [rcx+29h]
0x1800f462f  mov     rcx, [rbp+var_50]
0x1800f4633  mov     word ptr [rbp+var_40], ax
0x1800f4637  lea     rax, [rbp+var_28]
0x1800f463b  mov     [rbp+var_30], rax
0x1800f463f  movdqu  [rbp+var_24], xmm0
0x1800f4644  mov     rax, [rcx]
0x1800f4647  mov     rax, [rax+18h]
0x1800f464b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f4650  mov     rcx, [rbp+var_50]
0x1800f4654  mov     edi, eax
0x1800f4656  mov     rax, [rcx]
0x1800f4659  mov     rax, [rax+10h]
0x1800f465d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f4662  mov     rcx, [rbp+var_48]
0x1800f4666  mov     rax, [rcx]
0x1800f4669  mov     rax, [rax+10h]
0x1800f466d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f4672  test    edi, edi
0x1800f4674  jns     short loc_1800F46DD
0x1800f4676  mov     eax, edi
0x1800f4678  jmp     loc_1800F4777
0x1800f467d  lea     rdx, [rbx+0DCh]
0x1800f4684  mov     rax, [rdx]
0x1800f4687  sub     rax, qword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x1800f468e  jnz     short loc_1800F469B
0x1800f4690  mov     rax, [rdx+8]
0x1800f4694  sub     rax, qword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data4
0x1800f469b  test    rax, rax
0x1800f469e  setz    al
0x1800f46a1  xor     ecx, ecx
0x1800f46a3  test    al, al
0x1800f46a5  mov     rax, r9
0x1800f46a8  cmovz   rcx, rdx
0x1800f46ac  xor     r8d, r8d
0x1800f46af  mov     rdx, rsi
0x1800f46b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f46b7  mov     ecx, eax
0x1800f46b9  test    eax, eax
0x1800f46bb  jz      short loc_1800F46DD
0x1800f46bd  mov     eax, 6
0x1800f46c2  cmp     ecx, 8878000Ah
0x1800f46c8  lea     edx, [rax-2]
0x1800f46cb  cmovz   eax, edx
0x1800f46ce  jmp     loc_1800F4777
0x1800f46d3  mov     eax, 6
0x1800f46d8  jmp     loc_1800F4777
0x1800f46dd  test    r14d, r14d
0x1800f46e0  jnz     loc_1800F4775
0x1800f46e6  mov     rdx, [rbx+30h]
0x1800f46ea  test    rdx, rdx
0x1800f46ed  jnz     short loc_1800F4712
0x1800f46ef  call    cs:__imp_GetForegroundWindow
0x1800f46f6  nop     dword ptr [rax+rax+00h]
0x1800f46fb  mov     rdx, rax
0x1800f46fe  test    rax, rax
0x1800f4701  jnz     short loc_1800F4712
0x1800f4703  call    cs:__imp_GetDesktopWindow
0x1800f470a  nop     dword ptr [rax+rax+00h]
0x1800f470f  mov     rdx, rax
0x1800f4712  mov     rcx, [rsi]
0x1800f4715  mov     edi, 2
0x1800f471a  mov     r8d, edi
0x1800f471d  mov     rax, [rcx]
0x1800f4720  mov     rax, [rax+30h]
0x1800f4724  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f4729  test    eax, eax
0x1800f472b  jz      short loc_1800F4775
0x1800f472d  cmp     byte ptr [rbx+38h], 0
0x1800f4731  jnz     short loc_1800F4775
0x1800f4733  xor     ebx, ebx
0x1800f4735  call    cs:__imp_GetForegroundWindow
0x1800f473c  nop     dword ptr [rax+rax+00h]
0x1800f4741  mov     rdx, rax
0x1800f4744  test    rax, rax
0x1800f4747  jnz     short loc_1800F4758
0x1800f4749  call    cs:__imp_GetDesktopWindow
0x1800f4750  nop     dword ptr [rax+rax+00h]
0x1800f4755  mov     rdx, rax
0x1800f4758  mov     rcx, [rsi]
0x1800f475b  mov     r8d, edi
0x1800f475e  mov     rax, [rcx]
0x1800f4761  mov     rax, [rax+30h]
0x1800f4765  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f476a  test    eax, eax
0x1800f476c  jz      short loc_1800F4775
0x1800f476e  inc     ebx
0x1800f4770  cmp     ebx, 0Ah
0x1800f4773  jl      short loc_1800F4735
0x1800f4775  xor     eax, eax
0x1800f4777  mov     rcx, [rbp+var_10]
0x1800f477b  xor     rcx, rsp; StackCookie
0x1800f477e  call    __security_check_cookie
0x1800f4783  lea     r11, [rsp+80h+var_s0]
0x1800f478b  mov     rbx, [r11+28h]
0x1800f478f  mov     rsi, [r11+30h]
0x1800f4793  mov     rsp, r11
0x1800f4796  pop     r14
0x1800f4798  pop     rdi
0x1800f4799  pop     rbp
0x1800f479a  retn
```
