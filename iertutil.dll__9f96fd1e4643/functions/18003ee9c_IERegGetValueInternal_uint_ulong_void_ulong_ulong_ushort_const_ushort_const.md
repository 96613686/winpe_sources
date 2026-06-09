# IERegGetValueInternal(uint,ulong *,void *,ulong *,ulong *,ushort const *,ushort const *)

- ea: `0x18003ee9c`
- end: `0x18003f202`
- name: `?IERegGetValueInternal@@YAJIPEAKPEAX00PEBG2@Z`
- size: `870`
- prototype: `int(unsigned int, unsigned int *, void *, unsigned int *, unsigned int *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `5`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18003e9e0`
- `0x18003ea90`
- `0x18003ebec`
- `0x18003ec40`
- `0x1800677bc`

## callees

- `0x18003ee9c`
- `0x18003f340`
- `0x18003f5c0`
- `0x180083bc2`
- `0x180083c10`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18003f0f5`
- `msvcrt!memcpy_s` at `0x18003f0f5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003f008`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003f008`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003f04a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003f04a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003f058`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003f058`

## pseudocode

```c
__int64 __fastcall IERegGetValueInternal(
        unsigned int a1,
        unsigned int *a2,
        BYTE *a3,
        unsigned int *a4,
        unsigned int *a5,
        const unsigned __int16 *a6,
        const unsigned __int16 *a7)
{
  __int64 v10; // r14
  __int64 v11; // rcx
  char *v12; // rax
  const unsigned __int16 *v13; // rdx
  __int64 v14; // r9
  char *v15; // rcx
  int v16; // esi
  __int64 v17; // r15
  BOOL v18; // r14d
  HKEY v19; // rcx
  DWORD v20; // eax
  LSTATUS v21; // r14d
  unsigned int *v22; // rcx
  rsize_t v23; // r9
  _QWORD *v24; // r8
  unsigned int v26; // ecx
  DWORD v27; // eax
  DWORD Type; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v31; // [rsp+40h] [rbp-C0h]
  LPCWSTR lpSubKey; // [rsp+48h] [rbp-B8h]
  LPCWSTR lpValueName; // [rsp+50h] [rbp-B0h]
  WCHAR String1[18]; // [rsp+60h] [rbp-A0h] BYREF
  char v35; // [rsp+84h] [rbp-7Ch] BYREF
  char v36[490]; // [rsp+86h] [rbp-7Ah] BYREF

  lpSubKey = a6;
  lpValueName = a7;
  v10 = a1;
  IERegInit();
  if ( a3 && !a4 )
    return 2147747586LL;
  wcscpy(String1, L"Software\\Polices\\");
  memset_0(v36, 0, 0x1E2u);
  v11 = 2147483646;
  v12 = &v35;
  v13 = a6;
  v14 = 242;
  do
  {
    if ( !v11 )
      break;
    if ( !*v13 )
      break;
    *(_WORD *)v12 = *v13++;
    v12 += 2;
    --v11;
    --v14;
  }
  while ( v14 );
  v31 = v14;
  v15 = v12 - 2;
  v16 = 0;
  if ( v14 )
    v15 = v12;
  v17 = v10;
  *(_WORD *)v15 = 0;
  while ( v16 < 5 )
  {
    v18 = 1;
    if ( v16 <= 1 )
    {
      if ( v14 )
      {
        Type = 0;
        if ( (int)IERegQueryInfoKey(String1, v16 != 0, 0, &Type) >= 0 )
          v18 = Type != 0;
      }
    }
    if ( (dword_18025DFD0[v16] & dword_1800E4BA4[10 * v17]) == dword_18025DFD0[v16] )
    {
      v19 = (HKEY)qword_18029A190[v16];
      if ( v19 )
      {
        if ( v18 )
        {
          hKey = 0;
          if ( !RegOpenKeyExW(v19, lpSubKey, 0, 0x20019u, &hKey) )
          {
            Type = 0;
            v20 = a4 ? *a4 : 0;
            cbData = v20;
            v21 = RegQueryValueExW(hKey, lpValueName, 0, &Type, a3, &cbData);
            RegCloseKey(hKey);
            if ( !v21 || v21 == 234 )
            {
              v26 = dword_1800E4B90[10 * v17];
              if ( v26 == Type )
              {
                v27 = cbData;
                if ( cbData )
                {
                  if ( a2 )
                    *a2 = v26;
                  if ( a5 )
                    *a5 = v16;
                  if ( a4 )
                    *a4 = v27;
                  return v21 != 0 ? 0x80040702 : 0;
                }
              }
            }
          }
        }
      }
    }
    v14 = v31;
    ++v16;
  }
  if ( (dword_1800E4BA4[10 * v17] & 0x10) != 0 )
  {
    v22 = (unsigned int *)&_ImageBase[20 * v17 + 468424];
    if ( a2 )
      *a2 = *v22;
    if ( a5 )
      *a5 = 5;
    if ( !a3 )
    {
      if ( !a4 )
        return 0;
LABEL_36:
      *a4 = dword_1800E4BA0[10 * v17];
      return 0;
    }
    v23 = (unsigned int)dword_1800E4BA0[10 * v17];
    if ( *a4 >= (unsigned int)v23 )
    {
      v24 = &algn_1800E4B94[40 * v17 + 4];
      if ( *v22 != 4 )
        v24 = (_QWORD *)*v24;
      memcpy_s(a3, *a4, v24, v23);
      goto LABEL_36;
    }
    *a4 = v23;
    return 2147747586LL;
  }
  if ( a5 )
    *a5 = 6;
  return 2147747584LL;
}

```

## disassembly

```asm
0x18003ee9c  push    rbp
0x18003ee9e  push    rbx
0x18003ee9f  push    rsi
0x18003eea0  push    rdi
0x18003eea1  push    r12
0x18003eea3  push    r13
0x18003eea5  push    r14
0x18003eea7  push    r15
0x18003eea9  lea     rbp, [rsp-188h]
0x18003eeb1  sub     rsp, 288h
0x18003eeb8  mov     rax, cs:__security_cookie
0x18003eebf  xor     rax, rsp
0x18003eec2  mov     [rbp+1C0h+var_50], rax
0x18003eec9  mov     rax, [rbp+1C0h+arg_30]
0x18003eed0  mov     rbx, r9
0x18003eed3  mov     rsi, [rbp+1C0h+arg_28]
0x18003eeda  mov     r13, r8
0x18003eedd  mov     rdi, [rbp+1C0h+arg_20]
0x18003eee4  mov     r12, rdx
0x18003eee7  mov     [rsp+2C0h+lpSubKey], rsi
0x18003eeec  mov     [rsp+2C0h+lpValueName], rax
0x18003eef1  mov     r14d, ecx
0x18003eef4  call    IERegInit
0x18003eef9  test    r13, r13
0x18003eefc  jz      short loc_18003EF07
0x18003eefe  test    rbx, rbx
0x18003ef01  jz      loc_18003F1E0
0x18003ef07  movups  xmm0, xmmword ptr cs:aSoftwarePolici_12; "Software\\Policies\\"
0x18003ef0e  xor     edx, edx; Val
0x18003ef10  mov     r8d, 1E2h; Size
0x18003ef16  movups  xmm1, xmmword ptr cs:aSoftwarePolici_12+10h; "\\Policies\\"
0x18003ef1d  lea     rcx, [rbp+1C0h+var_23A]; void *
0x18003ef21  movaps  xmmword ptr [rsp+2C0h+String1], xmm0
0x18003ef26  movsd   xmm0, qword ptr cs:aSoftwarePolici_12+1Eh; "es\\"
0x18003ef2e  movaps  [rsp+2C0h+var_250], xmm1
0x18003ef33  movsd   qword ptr [rsp+2C0h+var_250+0Eh], xmm0
0x18003ef39  call    memset_0
0x18003ef3e  mov     ecx, 7FFFFFFEh
0x18003ef43  lea     rax, [rbp+1C0h+var_23C]
0x18003ef47  mov     rdx, rsi
0x18003ef4a  mov     r9d, 0F2h
0x18003ef50  xor     r10d, r10d
0x18003ef53  test    rcx, rcx
0x18003ef56  jz      short loc_18003EF77
0x18003ef58  movzx   r8d, word ptr [rdx]
0x18003ef5c  test    r8w, r8w
0x18003ef60  jz      short loc_18003EF77
0x18003ef62  mov     [rax], r8w
0x18003ef66  add     rdx, 2
0x18003ef6a  add     rax, 2
0x18003ef6e  dec     rcx
0x18003ef71  sub     r9, 1
0x18003ef75  jnz     short loc_18003EF53
0x18003ef77  test    r9, r9
0x18003ef7a  mov     [rsp+2C0h+var_280], r9
0x18003ef7f  lea     rcx, [rax-2]
0x18003ef83  mov     esi, r10d
0x18003ef86  cmovnz  rcx, rax
0x18003ef8a  lea     r8, __ImageBase
0x18003ef91  mov     r15, r14
0x18003ef94  mov     [rcx], r10w
0x18003ef98  cmp     esi, 5
0x18003ef9b  jge     loc_18003F08A
0x18003efa1  mov     r14d, 1
0x18003efa7  cmp     esi, r14d
0x18003efaa  jle     loc_18003F104
0x18003efb0  movsxd  rdx, esi
0x18003efb3  lea     rax, [r15+r15*4]
0x18003efb7  mov     eax, ds:rva dword_1800E4BA4[r8+rax*8]
0x18003efbf  mov     ecx, ds:rva dword_18025DFD0[r8+rdx*4]
0x18003efc7  and     eax, ecx
0x18003efc9  cmp     eax, ecx
0x18003efcb  jnz     loc_18003F07E
0x18003efd1  mov     rcx, rva qword_18029A190[r8+rdx*8]; hKey
0x18003efd9  test    rcx, rcx
0x18003efdc  jz      loc_18003F07E
0x18003efe2  test    r14d, r14d
0x18003efe5  jz      loc_18003F07E
0x18003efeb  mov     rdx, [rsp+2C0h+lpSubKey]; lpSubKey
0x18003eff0  lea     rax, [rsp+2C0h+hKey]
0x18003eff5  mov     r9d, 20019h; samDesired
0x18003effb  mov     [rsp+2C0h+phkResult], rax; phkResult
0x18003f000  xor     r8d, r8d; ulOptions
0x18003f003  mov     [rsp+2C0h+hKey], r10
0x18003f008  call    cs:__imp_RegOpenKeyExW
0x18003f00e  xor     r10d, r10d
0x18003f011  test    eax, eax
0x18003f013  jnz     short loc_18003F077
0x18003f015  mov     [rsp+2C0h+Type], r10d
0x18003f01a  test    rbx, rbx
0x18003f01d  jz      loc_18003F1EA
0x18003f023  mov     eax, [rbx]
0x18003f025  mov     rdx, [rsp+2C0h+lpValueName]; lpValueName
0x18003f02a  lea     r9, [rsp+2C0h+Type]; lpType
0x18003f02f  mov     rcx, [rsp+2C0h+hKey]; hKey
0x18003f034  xor     r8d, r8d; lpReserved
0x18003f037  mov     [rsp+2C0h+cbData], eax
0x18003f03b  lea     rax, [rsp+2C0h+cbData]
0x18003f040  mov     [rsp+2C0h+lpcbData], rax; lpcbData
0x18003f045  mov     [rsp+2C0h+phkResult], r13; lpData
0x18003f04a  call    cs:__imp_RegQueryValueExW
0x18003f050  mov     rcx, [rsp+2C0h+hKey]; hKey
0x18003f055  mov     r14d, eax
0x18003f058  call    cs:__imp_RegCloseKey
0x18003f05e  xor     r10d, r10d
0x18003f061  test    r14d, r14d
0x18003f064  jz      loc_18003F18C
0x18003f06a  cmp     r14d, 0EAh
0x18003f071  jz      loc_18003F18C
0x18003f077  lea     r8, __ImageBase
0x18003f07e  mov     r9, [rsp+2C0h+var_280]
0x18003f083  inc     esi
0x18003f085  jmp     loc_18003EF98
0x18003f08a  lea     r9, [r15+r15*4]
0x18003f08e  test    byte ptr ds:rva dword_1800E4BA4[r8+r9*8], 10h
0x18003f097  jz      loc_18003F180
0x18003f09d  lea     rcx, ds:0E4B90h[r9*8]
0x18003f0a5  add     rcx, r8
0x18003f0a8  test    r12, r12
0x18003f0ab  jz      short loc_18003F0B3
0x18003f0ad  mov     eax, [rcx]
0x18003f0af  mov     [r12], eax
0x18003f0b3  test    rdi, rdi
0x18003f0b6  jz      short loc_18003F0BE
0x18003f0b8  mov     dword ptr [rdi], 5
0x18003f0be  test    r13, r13
0x18003f0c1  jz      loc_18003F148
0x18003f0c7  mov     r9d, ds:rva dword_1800E4BA0[r8+r9*8]; SourceSize
0x18003f0cf  cmp     [rbx], r9d
0x18003f0d2  jb      loc_18003F1DD
0x18003f0d8  cmp     dword ptr [rcx], 4
0x18003f0db  lea     rax, [r15+r15*4]
0x18003f0df  mov     edx, [rbx]; DestinationSize
0x18003f0e1  lea     r8, [r8+rax*8]
0x18003f0e5  lea     r8, [r8+0E4B98h]; Source
0x18003f0ec  mov     rcx, r13; Destination
0x18003f0ef  jnz     loc_18003F1F2
0x18003f0f5  call    cs:__imp_memcpy_s
0x18003f0fb  lea     r8, __ImageBase
0x18003f102  jmp     short loc_18003F14D
0x18003f104  test    esi, esi
0x18003f106  mov     edx, r10d
0x18003f109  setnz   dl; int
0x18003f10c  test    r9, r9
0x18003f10f  jz      loc_18003EFB0
0x18003f115  lea     r9, [rsp+2C0h+Type]; unsigned int *
0x18003f11a  mov     [rsp+2C0h+Type], r10d
0x18003f11f  xor     r8d, r8d; unsigned int *
0x18003f122  lea     rcx, [rsp+2C0h+String1]; lpString1
0x18003f127  call    ?IERegQueryInfoKey@@YAJPEBGHPEAK1@Z; IERegQueryInfoKey(ushort const *,int,ulong *,ulong *)
0x18003f12c  xor     r10d, r10d
0x18003f12f  test    eax, eax
0x18003f131  js      short loc_18003F13C
0x18003f133  cmp     [rsp+2C0h+Type], r10d
0x18003f138  cmovz   r14d, r10d
0x18003f13c  lea     r8, __ImageBase
0x18003f143  jmp     loc_18003EFB0
0x18003f148  test    rbx, rbx
0x18003f14b  jz      short loc_18003F15B
0x18003f14d  lea     rax, [r15+r15*4]
0x18003f151  mov     eax, ds:rva dword_1800E4BA0[r8+rax*8]
0x18003f159  mov     [rbx], eax
0x18003f15b  xor     eax, eax
0x18003f15d  mov     rcx, [rbp+1C0h+var_50]
0x18003f164  xor     rcx, rsp; StackCookie
0x18003f167  call    __security_check_cookie
0x18003f16c  add     rsp, 288h
0x18003f173  pop     r15
0x18003f175  pop     r14
0x18003f177  pop     r13
0x18003f179  pop     r12
0x18003f17b  pop     rdi
0x18003f17c  pop     rsi
0x18003f17d  pop     rbx
0x18003f17e  pop     rbp
0x18003f17f  retn
0x18003f180  test    rdi, rdi
0x18003f183  jnz     short loc_18003F1FA
0x18003f185  mov     eax, 80040700h
0x18003f18a  jmp     short loc_18003F15D
0x18003f18c  lea     rcx, [r15+r15*4]
0x18003f190  lea     r8, __ImageBase
0x18003f197  mov     ecx, ds:rva dword_1800E4B90[r8+rcx*8]
0x18003f19f  cmp     ecx, [rsp+2C0h+Type]
0x18003f1a3  jnz     loc_18003F07E
0x18003f1a9  mov     eax, [rsp+2C0h+cbData]
0x18003f1ad  test    eax, eax
0x18003f1af  jz      loc_18003F07E
0x18003f1b5  test    r12, r12
0x18003f1b8  jz      short loc_18003F1BE
0x18003f1ba  mov     [r12], ecx
0x18003f1be  test    rdi, rdi
0x18003f1c1  jz      short loc_18003F1C5
0x18003f1c3  mov     [rdi], esi
0x18003f1c5  test    rbx, rbx
0x18003f1c8  jz      short loc_18003F1CC
0x18003f1ca  mov     [rbx], eax
0x18003f1cc  mov     eax, r10d
0x18003f1cf  sub     eax, r14d
0x18003f1d2  neg     eax
0x18003f1d4  sbb     eax, eax
0x18003f1d6  and     eax, 80040702h
0x18003f1db  jmp     short loc_18003F15D
0x18003f1dd  mov     [rbx], r9d
0x18003f1e0  mov     eax, 80040702h
0x18003f1e5  jmp     loc_18003F15D
0x18003f1ea  mov     eax, r10d
0x18003f1ed  jmp     loc_18003F025
0x18003f1f2  mov     r8, [r8]
0x18003f1f5  jmp     loc_18003F0F5
0x18003f1fa  mov     dword ptr [rdi], 6
0x18003f200  jmp     short loc_18003F185
```
