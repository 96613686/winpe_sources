# CSecurityAdmin2::FormalizeUserName(ushort *,ushort * *,int)

- ea: `0x18002a350`
- end: `0x18002a594`
- name: `?FormalizeUserName@CSecurityAdmin2@@UEAAJPEAGPEAPEAGH@Z`
- size: `580`
- prototype: `int(CSecurityAdmin2 *__hidden this, unsigned __int16 *, unsigned __int16 **, int)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x180001e60`
- `0x180015594`
- `0x18001c6a4`
- `0x1800275d4`
- `0x18002a350`
- `0x18002a69c`
- `0x18002a850`
- `0x18005583a`
- `0x180055880`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18002a48f`
- `msvcrt!_wcsicmp` at `0x18002a4a8`
- `msvcrt!_wcsicmp` at `0x18002a48f`
- `msvcrt!_wcsicmp` at `0x18002a4a8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a55e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a55e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002a504`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002a504`

## pseudocode

```c
int __fastcall CSecurityAdmin2::FormalizeUserName(CSecurityAdmin2 *this, unsigned __int16 *a2, LPVOID *a3, int a4)
{
  int result; // eax
  int v8; // eax
  CGetAccountDomain *v9; // rcx
  int v10; // r10d
  unsigned __int16 v11; // di
  __int64 v12; // r11
  __int64 v13; // rax
  __int64 v14; // rcx
  SIZE_T v15; // rbx
  unsigned __int16 *v16; // rax
  int v17; // eax
  int v18; // ebx
  wchar_t *String2; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t String1[280]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 v21[280]; // [rsp+270h] [rbp+170h] BYREF

  memset_0(String1, 0, 0x222u);
  memset_0(v21, 0, 0x222u);
  *a3 = 0;
  if ( (int)safe_lstrlenW(a2) >= 273 )
    return -2147024809;
  while ( 1 )
  {
    v8 = safe_lstrlenW(a2);
    if ( v10 >= v8 )
      break;
    v11 = a2[v10];
    if ( v11 == 92 || v11 == 47 )
    {
      a2[v10] = 0;
      result = StringCchCopyW(String1, 0x111u, a2);
      if ( result < 0 )
        return result;
      a2[v12] = v11;
      result = StringCchCopyW(v21, 0x111u, &a2[v12 + 1]);
      if ( result < 0 )
        return result;
    }
  }
  if ( String1[0] || (result = StringCchCopyW(v21, 0x111u, a2), result >= 0) )
  {
    result = CGetAccountDomain::Init(v9);
    if ( result >= 0 )
    {
      String2 = 0;
      result = GetLocalizedBUILTIN(&String2);
      if ( result >= 0 )
      {
        if ( _wcsicmp(String1, L".") && (!a4 || _wcsicmp(String1, String2))
          || (result = StringCchCopyW(String1, 0x111u, qword_1800733E8), result >= 0) )
        {
          v13 = -1;
          v14 = -1;
          do
            ++v14;
          while ( String1[v14] );
          do
            ++v13;
          while ( v21[v13] );
          v15 = (unsigned int)(2 * (v14 + v13) + 4);
          v16 = (unsigned __int16 *)CoTaskMemAlloc(v15);
          *a3 = v16;
          if ( v16 )
          {
            if ( String1[0] )
              v17 = StringCbPrintfW(v16, v15, L"%s\\%s", String1, v21);
            else
              v17 = StringCbCopyW(v16, v15, v21);
            v18 = v17;
            if ( v17 < 0 )
            {
              CoTaskMemFree(*a3);
              *a3 = 0;
            }
            return v18;
          }
          else
          {
            return -2147024882;
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18002a350  mov     [rsp-8+arg_0], rbx
0x18002a355  mov     [rsp-8+arg_18], rsi
0x18002a35a  push    rbp
0x18002a35b  push    rdi
0x18002a35c  push    r12
0x18002a35e  push    r14
0x18002a360  push    r15
0x18002a362  lea     rbp, [rsp-3B0h]
0x18002a36a  sub     rsp, 4B0h
0x18002a371  mov     rax, cs:__security_cookie
0x18002a378  xor     rax, rsp
0x18002a37b  mov     [rbp+3D0h+var_30], rax
0x18002a382  mov     rsi, r8
0x18002a385  lea     rcx, [rsp+4D0h+String1]; void *
0x18002a38a  mov     rbx, rdx
0x18002a38d  mov     edi, 222h
0x18002a392  mov     r8d, edi; Size
0x18002a395  xor     edx, edx; Val
0x18002a397  mov     r14d, r9d
0x18002a39a  call    memset_0
0x18002a39f  mov     r8d, edi; Size
0x18002a3a2  lea     rcx, [rbp+3D0h+var_260]; void *
0x18002a3a9  xor     edx, edx; Val
0x18002a3ab  call    memset_0
0x18002a3b0  xor     r15d, r15d
0x18002a3b3  mov     rcx, rbx; unsigned __int16 *
0x18002a3b6  mov     [rsi], r15
0x18002a3b9  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x18002a3be  mov     r12d, 111h
0x18002a3c4  cmp     eax, r12d
0x18002a3c7  jl      short loc_18002A3D3
0x18002a3c9  mov     eax, 80070057h
0x18002a3ce  jmp     loc_18002A569
0x18002a3d3  mov     r10d, r15d
0x18002a3d6  mov     rcx, rbx; unsigned __int16 *
0x18002a3d9  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x18002a3de  cmp     r10d, eax
0x18002a3e1  jge     short loc_18002A43D
0x18002a3e3  movsxd  r11, r10d
0x18002a3e6  movzx   edi, word ptr [rbx+r11*2]
0x18002a3eb  cmp     di, 5Ch ; '\'
0x18002a3ef  jz      short loc_18002A3F7
0x18002a3f1  cmp     di, 2Fh ; '/'
0x18002a3f5  jnz     short loc_18002A438
0x18002a3f7  mov     r8, rbx; unsigned __int16 *
0x18002a3fa  mov     [rbx+r11*2], r15w
0x18002a3ff  mov     rdx, r12; unsigned __int64
0x18002a402  lea     rcx, [rsp+4D0h+String1]; unsigned __int16 *
0x18002a407  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002a40c  test    eax, eax
0x18002a40e  js      loc_18002A569
0x18002a414  lea     r8, [rbx+2]
0x18002a418  mov     [rbx+r11*2], di
0x18002a41d  lea     r8, [r8+r11*2]; unsigned __int16 *
0x18002a421  mov     rdx, r12; unsigned __int64
0x18002a424  lea     rcx, [rbp+3D0h+var_260]; unsigned __int16 *
0x18002a42b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002a430  test    eax, eax
0x18002a432  js      loc_18002A569
0x18002a438  inc     r10d
0x18002a43b  jmp     short loc_18002A3D6
0x18002a43d  cmp     [rsp+4D0h+String1], r15w
0x18002a443  jnz     short loc_18002A45F
0x18002a445  mov     r8, rbx; unsigned __int16 *
0x18002a448  lea     rcx, [rbp+3D0h+var_260]; unsigned __int16 *
0x18002a44f  mov     rdx, r12; unsigned __int64
0x18002a452  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002a457  test    eax, eax
0x18002a459  js      loc_18002A569
0x18002a45f  call    ?Init@CGetAccountDomain@@QEAAJXZ; CGetAccountDomain::Init(void)
0x18002a464  test    eax, eax
0x18002a466  js      loc_18002A569
0x18002a46c  lea     rcx, [rsp+4D0h+String2]; unsigned __int16 **
0x18002a471  mov     [rsp+4D0h+String2], r15
0x18002a476  call    ?GetLocalizedBUILTIN@@YAJPEAPEAG@Z; GetLocalizedBUILTIN(ushort * *)
0x18002a47b  test    eax, eax
0x18002a47d  js      loc_18002A569
0x18002a483  lea     rdx, asc_180064E8C; "."
0x18002a48a  lea     rcx, [rsp+4D0h+String1]; String1
0x18002a48f  call    cs:__imp__wcsicmp
0x18002a495  test    eax, eax
0x18002a497  jz      short loc_18002A4B2
0x18002a499  test    r14d, r14d
0x18002a49c  jz      short loc_18002A4CE
0x18002a49e  mov     rdx, [rsp+4D0h+String2]; String2
0x18002a4a3  lea     rcx, [rsp+4D0h+String1]; String1
0x18002a4a8  call    cs:__imp__wcsicmp
0x18002a4ae  test    eax, eax
0x18002a4b0  jnz     short loc_18002A4CE
0x18002a4b2  mov     r8, cs:qword_1800733E8; unsigned __int16 *
0x18002a4b9  lea     rcx, [rsp+4D0h+String1]; unsigned __int16 *
0x18002a4be  mov     rdx, r12; unsigned __int64
0x18002a4c1  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002a4c6  test    eax, eax
0x18002a4c8  js      loc_18002A569
0x18002a4ce  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002a4d2  lea     rdx, [rsp+4D0h+String1]
0x18002a4d7  mov     rcx, rax
0x18002a4da  inc     rcx
0x18002a4dd  cmp     [rdx+rcx*2], r15w
0x18002a4e2  jnz     short loc_18002A4DA
0x18002a4e4  lea     rdx, [rbp+3D0h+var_260]
0x18002a4eb  inc     rax
0x18002a4ee  cmp     [rdx+rax*2], r15w
0x18002a4f3  jnz     short loc_18002A4EB
0x18002a4f5  add     rax, rcx
0x18002a4f8  lea     rax, ds:4[rax*2]
0x18002a500  mov     ecx, eax; cb
0x18002a502  mov     ebx, eax
0x18002a504  call    cs:__imp_CoTaskMemAlloc
0x18002a50a  mov     [rsi], rax
0x18002a50d  test    rax, rax
0x18002a510  jnz     short loc_18002A519
0x18002a512  mov     eax, 8007000Eh
0x18002a517  jmp     short loc_18002A569
0x18002a519  mov     rdx, rbx; unsigned __int64
0x18002a51c  cmp     [rsp+4D0h+String1], r15w
0x18002a522  jz      short loc_18002A546
0x18002a524  lea     rcx, [rbp+3D0h+var_260]
0x18002a52b  mov     [rsp+4D0h+var_4B0], rcx
0x18002a530  lea     r9, [rsp+4D0h+String1]
0x18002a535  mov     rcx, rax; unsigned __int16 *
0x18002a538  lea     r8, aSS_0; "%s\\%s"
0x18002a53f  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002a544  jmp     short loc_18002A555
0x18002a546  lea     r8, [rbp+3D0h+var_260]; unsigned __int16 *
0x18002a54d  mov     rcx, rax; unsigned __int16 *
0x18002a550  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x18002a555  mov     ebx, eax
0x18002a557  test    eax, eax
0x18002a559  jns     short loc_18002A567
0x18002a55b  mov     rcx, [rsi]; pv
0x18002a55e  call    cs:__imp_CoTaskMemFree
0x18002a564  mov     [rsi], r15
0x18002a567  mov     eax, ebx
0x18002a569  mov     rcx, [rbp+3D0h+var_30]
0x18002a570  xor     rcx, rsp; StackCookie
0x18002a573  call    __security_check_cookie
0x18002a578  lea     r11, [rsp+4D0h+var_20]
0x18002a580  mov     rbx, [r11+30h]
0x18002a584  mov     rsi, [r11+48h]
0x18002a588  mov     rsp, r11
0x18002a58b  pop     r15
0x18002a58d  pop     r14
0x18002a58f  pop     r12
0x18002a591  pop     rdi
0x18002a592  pop     rbp
0x18002a593  retn
```
