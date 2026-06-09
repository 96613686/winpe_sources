# DeviceLocHelper::GetDisplayName(ushort const *,ushort *,ulong)

- ea: `0x1800117a8`
- end: `0x180011a2d`
- name: `?GetDisplayName@DeviceLocHelper@@QEAAJPEBGPEAGK@Z`
- size: `645`
- prototype: `__int64 __fastcall(DeviceLocHelper *this, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180011a34`

## callees

- `0x180009ff4`
- `0x1800117a8`
- `0x1800184ce`
- `0x180018500`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180011867`
- `KERNEL32!GetLastError` at `0x1800118c4`
- `KERNEL32!GetLastError` at `0x180011924`
- `KERNEL32!GetLastError` at `0x1800119e7`
- `KERNEL32!GetLastError` at `0x180011867`
- `KERNEL32!GetLastError` at `0x1800118c4`
- `KERNEL32!GetLastError` at `0x180011924`
- `KERNEL32!GetLastError` at `0x1800119e7`
- `KERNEL32!lstrcmpW` at `0x18001194d`
- `KERNEL32!lstrcmpW` at `0x18001198f`
- `KERNEL32!lstrcmpW` at `0x18001194d`
- `KERNEL32!lstrcmpW` at `0x18001198f`
- `DEVOBJ!DevObjGetDeviceProperty` at `0x1800119dd`
- `DEVOBJ!DevObjGetDeviceProperty` at `0x1800119dd`
- `DEVOBJ!DevObjEnumDeviceInfo` at `0x18001185d`
- `DEVOBJ!DevObjEnumDeviceInfo` at `0x18001185d`
- `DEVOBJ!DevObjGetDeviceRegistryProperty` at `0x1800118ba`
- `DEVOBJ!DevObjGetDeviceRegistryProperty` at `0x18001191a`
- `DEVOBJ!DevObjGetDeviceRegistryProperty` at `0x1800118ba`
- `DEVOBJ!DevObjGetDeviceRegistryProperty` at `0x18001191a`

## pseudocode

```c
__int64 __fastcall DeviceLocHelper::GetDisplayName(
        DeviceLocHelper *this,
        const unsigned __int16 *a2,
        unsigned __int16 *a3)
{
  signed int v3; // ebx
  unsigned int v7; // esi
  __int64 v8; // rcx
  signed int LastError; // eax
  signed int v10; // eax
  signed int v11; // eax
  __int64 v12; // rcx
  signed int v13; // eax
  int v15; // [rsp+40h] [rbp-C0h] BYREF
  _OWORD v16[3]; // [rsp+48h] [rbp-B8h] BYREF
  DEVPROPKEY v17; // [rsp+78h] [rbp-88h] BYREF
  WCHAR String2[264]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v19[528]; // [rsp+2A0h] [rbp+1A0h] BYREF
  WCHAR v20[264]; // [rsp+4B0h] [rbp+3B0h] BYREF

  v3 = *((_DWORD *)this + 2);
  memset_0(String2, 0, 0x208u);
  memset_0(v19, 0, 0x208u);
  v15 = 0;
  memset(v16, 0, sizeof(v16));
  v17 = DEVPKEY_NAME;
  memset_0(v20, 0, 0x208u);
  v7 = 0;
  while ( v3 >= 0 )
  {
    v8 = *(_QWORD *)this;
    LODWORD(v16[0]) = 48;
    if ( (unsigned int)DevObjEnumDeviceInfo(v8, v7, v16) )
      goto LABEL_34;
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v3 = -2147467259;
    }
    if ( v3 >= 0 )
    {
LABEL_34:
      if ( (unsigned int)DevObjGetDeviceRegistryProperty(*(_QWORD *)this, v16, 1, &v15, String2, 520, 0) )
        goto LABEL_35;
      v10 = GetLastError();
      v3 = v10;
      if ( v10 )
      {
        if ( v10 > 0 )
          v3 = (unsigned __int16)v10 | 0x80070000;
      }
      else
      {
        v3 = -2147467259;
      }
      if ( v3 >= 0 )
      {
LABEL_35:
        if ( (unsigned int)DevObjGetDeviceRegistryProperty(*(_QWORD *)this, v16, 9, &v15, v19, 520, 0) )
          goto LABEL_36;
        v11 = GetLastError();
        v3 = v11;
        if ( v11 )
        {
          if ( v11 > 0 )
            v3 = (unsigned __int16)v11 | 0x80070000;
        }
        else
        {
          v3 = -2147467259;
        }
        if ( v3 >= 0 )
        {
LABEL_36:
          if ( !lstrcmpW(a2, String2)
            || (v3 = StringCchPrintfW(v20, 0x104u, L"%s\\%s", String2, v19), v3 >= 0) && !lstrcmpW(a2, v20) )
          {
            v12 = *(_QWORD *)this;
            v15 = 0;
            if ( !(unsigned int)((__int64 (__fastcall *)(__int64, _OWORD *, DEVPROPKEY *, int *, unsigned __int16 *, int, _QWORD, _DWORD))DevObjGetDeviceProperty)(
                                  v12,
                                  v16,
                                  &v17,
                                  &v15,
                                  a3,
                                  440,
                                  0,
                                  0) )
            {
              v13 = GetLastError();
              v3 = v13;
              if ( v13 )
              {
                if ( v13 > 0 )
                  return (unsigned __int16)v13 | 0x80070000;
              }
              else
              {
                return (unsigned int)-2147467259;
              }
            }
            return (unsigned int)v3;
          }
        }
      }
    }
    ++v7;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800117a8  mov     [rsp-8+arg_18], rbx
0x1800117ad  push    rbp
0x1800117ae  push    rsi
0x1800117af  push    rdi
0x1800117b0  push    r14
0x1800117b2  push    r15
0x1800117b4  lea     rbp, [rsp-5D0h]
0x1800117bc  sub     rsp, 6D0h
0x1800117c3  mov     rax, cs:__security_cookie
0x1800117ca  xor     rax, rsp
0x1800117cd  mov     [rbp+5F0h+var_30], rax
0x1800117d4  mov     ebx, [rcx+8]
0x1800117d7  mov     r15, r8
0x1800117da  mov     r14, rdx
0x1800117dd  mov     rdi, rcx
0x1800117e0  mov     esi, 208h
0x1800117e5  lea     rcx, [rbp+5F0h+String2]; void *
0x1800117e9  mov     r8d, esi; Size
0x1800117ec  xor     edx, edx; Val
0x1800117ee  call    memset_0
0x1800117f3  mov     r8d, esi; Size
0x1800117f6  lea     rcx, [rbp+5F0h+var_450]; void *
0x1800117fd  xor     edx, edx; Val
0x1800117ff  call    memset_0
0x180011804  mov     eax, cs:DEVPKEY_NAME.pid
0x18001180a  lea     rcx, [rbp+5F0h+var_240]; void *
0x180011811  xorps   xmm0, xmm0
0x180011814  mov     [rsp+6F0h+var_6B0], 0
0x18001181c  movups  [rsp+6F0h+var_6A8], xmm0
0x180011821  mov     r8d, esi; Size
0x180011824  xor     edx, edx; Val
0x180011826  movups  [rsp+6F0h+var_698], xmm0
0x18001182b  mov     [rbp+5F0h+var_668], eax
0x18001182e  movups  [rsp+6F0h+var_688], xmm0
0x180011833  movups  xmm0, xmmword ptr cs:DEVPKEY_NAME.fmtid.Data1
0x18001183a  movups  [rsp+6F0h+var_678], xmm0
0x18001183f  call    memset_0
0x180011844  xor     esi, esi
0x180011846  jmp     loc_18001199B
0x18001184b  mov     rcx, [rdi]
0x18001184e  lea     r8, [rsp+6F0h+var_6A8]
0x180011853  mov     edx, esi
0x180011855  mov     dword ptr [rsp+6F0h+var_6A8], 30h ; '0'
0x18001185d  call    cs:__imp_DevObjEnumDeviceInfo
0x180011863  test    eax, eax
0x180011865  jnz     short loc_18001188D
0x180011867  call    cs:__imp_GetLastError
0x18001186d  mov     ebx, eax
0x18001186f  test    eax, eax
0x180011871  jz      short loc_180011880
0x180011873  jle     short loc_180011885
0x180011875  movzx   ebx, ax
0x180011878  or      ebx, 80070000h
0x18001187e  jmp     short loc_180011885
0x180011880  mov     ebx, 80004005h
0x180011885  test    ebx, ebx
0x180011887  js      loc_180011999
0x18001188d  mov     rcx, [rdi]
0x180011890  lea     rax, [rbp+5F0h+String2]
0x180011894  mov     [rsp+6F0h+var_6C0], 0
0x18001189d  lea     r9, [rsp+6F0h+var_6B0]
0x1800118a2  mov     [rsp+6F0h+var_6C8], 208h
0x1800118aa  lea     rdx, [rsp+6F0h+var_6A8]
0x1800118af  mov     r8d, 1
0x1800118b5  mov     [rsp+6F0h+var_6D0], rax
0x1800118ba  call    cs:__imp_DevObjGetDeviceRegistryProperty
0x1800118c0  test    eax, eax
0x1800118c2  jnz     short loc_1800118EA
0x1800118c4  call    cs:__imp_GetLastError
0x1800118ca  mov     ebx, eax
0x1800118cc  test    eax, eax
0x1800118ce  jz      short loc_1800118DD
0x1800118d0  jle     short loc_1800118E2
0x1800118d2  movzx   ebx, ax
0x1800118d5  or      ebx, 80070000h
0x1800118db  jmp     short loc_1800118E2
0x1800118dd  mov     ebx, 80004005h
0x1800118e2  test    ebx, ebx
0x1800118e4  js      loc_180011999
0x1800118ea  mov     rcx, [rdi]
0x1800118ed  lea     rax, [rbp+5F0h+var_450]
0x1800118f4  mov     [rsp+6F0h+var_6C0], 0
0x1800118fd  lea     r9, [rsp+6F0h+var_6B0]
0x180011902  mov     [rsp+6F0h+var_6C8], 208h
0x18001190a  lea     rdx, [rsp+6F0h+var_6A8]
0x18001190f  mov     r8d, 9
0x180011915  mov     [rsp+6F0h+var_6D0], rax
0x18001191a  call    cs:__imp_DevObjGetDeviceRegistryProperty
0x180011920  test    eax, eax
0x180011922  jnz     short loc_180011946
0x180011924  call    cs:__imp_GetLastError
0x18001192a  mov     ebx, eax
0x18001192c  test    eax, eax
0x18001192e  jz      short loc_18001193D
0x180011930  jle     short loc_180011942
0x180011932  movzx   ebx, ax
0x180011935  or      ebx, 80070000h
0x18001193b  jmp     short loc_180011942
0x18001193d  mov     ebx, 80004005h
0x180011942  test    ebx, ebx
0x180011944  js      short loc_180011999
0x180011946  lea     rdx, [rbp+5F0h+String2]; lpString2
0x18001194a  mov     rcx, r14; lpString1
0x18001194d  call    cs:__imp_lstrcmpW
0x180011953  test    eax, eax
0x180011955  jz      short loc_1800119A5
0x180011957  lea     rax, [rbp+5F0h+var_450]
0x18001195e  mov     edx, 104h; unsigned __int64
0x180011963  lea     r9, [rbp+5F0h+String2]
0x180011967  mov     [rsp+6F0h+var_6D0], rax
0x18001196c  lea     r8, aSS; "%s\\%s"
0x180011973  lea     rcx, [rbp+5F0h+var_240]; unsigned __int16 *
0x18001197a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001197f  mov     ebx, eax
0x180011981  test    eax, eax
0x180011983  js      short loc_180011999
0x180011985  lea     rdx, [rbp+5F0h+var_240]; lpString2
0x18001198c  mov     rcx, r14; lpString1
0x18001198f  call    cs:__imp_lstrcmpW
0x180011995  test    eax, eax
0x180011997  jz      short loc_1800119A5
0x180011999  inc     esi
0x18001199b  test    ebx, ebx
0x18001199d  jns     loc_18001184B
0x1800119a3  jmp     short loc_180011A05
0x1800119a5  mov     rcx, [rdi]
0x1800119a8  lea     r9, [rsp+6F0h+var_6B0]
0x1800119ad  mov     [rsp+6F0h+var_6B8], 0
0x1800119b5  lea     r8, [rsp+6F0h+var_678]
0x1800119ba  mov     [rsp+6F0h+var_6C0], 0
0x1800119c3  lea     rdx, [rsp+6F0h+var_6A8]
0x1800119c8  mov     [rsp+6F0h+var_6C8], 1B8h
0x1800119d0  mov     [rsp+6F0h+var_6D0], r15
0x1800119d5  mov     [rsp+6F0h+var_6B0], 0
0x1800119dd  call    cs:__imp_DevObjGetDeviceProperty
0x1800119e3  test    eax, eax
0x1800119e5  jnz     short loc_180011A05
0x1800119e7  call    cs:__imp_GetLastError
0x1800119ed  mov     ebx, eax
0x1800119ef  test    eax, eax
0x1800119f1  jz      short loc_180011A00
0x1800119f3  jle     short loc_180011A05
0x1800119f5  movzx   ebx, ax
0x1800119f8  or      ebx, 80070000h
0x1800119fe  jmp     short loc_180011A05
0x180011a00  mov     ebx, 80004005h
0x180011a05  mov     eax, ebx
0x180011a07  mov     rcx, [rbp+5F0h+var_30]
0x180011a0e  xor     rcx, rsp; StackCookie
0x180011a11  call    __security_check_cookie
0x180011a16  mov     rbx, [rsp+6F0h+arg_18]
0x180011a1e  add     rsp, 6D0h
0x180011a25  pop     r15
0x180011a27  pop     r14
0x180011a29  pop     rdi
0x180011a2a  pop     rsi
0x180011a2b  pop     rbp
0x180011a2c  retn
```
