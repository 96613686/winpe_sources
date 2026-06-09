# ColorDataController::EnumerateProfiles(WCS_PROFILE_MANAGEMENT_SCOPE,ushort const *,ulong,int *,Array<Profile> *)

- ea: `0x180011050`
- end: `0x180011310`
- name: `?EnumerateProfiles@ColorDataController@@AEBAJW4WCS_PROFILE_MANAGEMENT_SCOPE@@PEBGKPEAHPEAV?$Array@UProfile@@@@@Z`
- size: `704`
- prototype: `__int64 __fastcall(__int64, WCS_PROFILE_MANAGEMENT_SCOPE, const WCHAR *, DWORD, _DWORD *, HDSA *)`
- caller_count: `4`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x18000e558`
- `0x18000f9c0`
- `0x180010780`
- `0x1800173f8`

## callees

- `0x180001340`
- `0x18000138c`
- `0x180011050`
- `0x180011318`
- `0x1800180a4`
- `0x1800184ce`
- `0x180018500`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001114d`
- `KERNEL32!GetLastError` at `0x180011172`
- `KERNEL32!GetLastError` at `0x1800111e1`
- `KERNEL32!GetLastError` at `0x18001114d`
- `KERNEL32!GetLastError` at `0x180011172`
- `KERNEL32!GetLastError` at `0x1800111e1`
- `mscms!WcsEnumColorProfiles` at `0x18001113f`
- `mscms!WcsEnumColorProfiles` at `0x1800111d7`
- `mscms!WcsEnumColorProfiles` at `0x18001113f`
- `mscms!WcsEnumColorProfiles` at `0x1800111d7`
- `mscms!WcsEnumColorProfilesSize` at `0x180011168`
- `mscms!WcsEnumColorProfilesSize` at `0x180011168`

## pseudocode

```c
__int64 __fastcall ColorDataController::EnumerateProfiles(
        __int64 a1,
        WCS_PROFILE_MANAGEMENT_SCOPE a2,
        const WCHAR *a3,
        DWORD a4,
        _DWORD *a5,
        HDSA *a6)
{
  DWORD v9; // eax
  BYTE *v10; // rdi
  signed int v11; // ebx
  ColorDataController *v12; // rcx
  signed int LastError; // eax
  signed int v14; // eax
  const unsigned __int16 *v15; // rsi
  int v16; // eax
  const unsigned __int16 *v17; // rax
  __int64 v18; // rdx
  DWORD pdwSize; // [rsp+30h] [rbp-D0h] BYREF
  DWORD pnProfiles[3]; // [rsp+34h] [rbp-CCh] BYREF
  tagENUMTYPEW pEnumRecord; // [rsp+40h] [rbp-C0h] BYREF
  int pitem; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v24; // [rsp+A4h] [rbp-5Ch]
  __int16 v25; // [rsp+ACh] [rbp-54h]
  __int16 v26; // [rsp+2B4h] [rbp+1B4h]
  __int64 v27; // [rsp+4BCh] [rbp+3BCh]

  memset_0(&pEnumRecord.dwFields, 0, 0x58u);
  pdwSize = 0;
  v9 = 0;
  pnProfiles[0] = 0;
  pEnumRecord.dwSize = 96;
  pEnumRecord.dwVersion = 768;
  if ( a3 )
  {
    pEnumRecord.dwFields = 1;
    v9 = 1;
    pEnumRecord.pDeviceName = a3;
    if ( a5 )
    {
      v9 = *a5 != 0 ? 262145 : 131073;
      pEnumRecord.dwFields = v9;
    }
  }
  if ( a4 )
  {
    pEnumRecord.dwDeviceClass = a4;
    pEnumRecord.dwFields = v9 | 0x10000;
  }
  v10 = (BYTE *)operator new[](0xA00u);
  if ( !v10 )
  {
LABEL_7:
    v11 = -2147024882;
    goto LABEL_38;
  }
  v11 = 0;
  if ( WcsEnumColorProfiles(a2, &pEnumRecord, v10, 0xA00u, pnProfiles) )
    goto LABEL_21;
  LastError = GetLastError();
  if ( LastError != 122 )
  {
    if ( LastError <= 0 )
    {
      v11 = LastError;
      goto LABEL_38;
    }
    goto LABEL_13;
  }
  if ( !WcsEnumColorProfilesSize(a2, &pEnumRecord, &pdwSize) )
  {
    LastError = GetLastError();
    v11 = LastError;
    if ( LastError )
    {
      if ( LastError <= 0 )
        goto LABEL_38;
LABEL_13:
      v11 = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_38;
    }
LABEL_37:
    v11 = -2147467259;
    goto LABEL_38;
  }
  if ( !pdwSize )
    goto LABEL_38;
  operator delete[](v10);
  v10 = (BYTE *)operator new[](pdwSize);
  if ( !v10 )
    goto LABEL_7;
  if ( WcsEnumColorProfiles(a2, &pEnumRecord, v10, pdwSize, pnProfiles) )
    goto LABEL_21;
  v14 = GetLastError();
  v11 = v14;
  if ( !v14 )
    goto LABEL_37;
  if ( v14 > 0 )
    v11 = (unsigned __int16)v14 | 0x80070000;
  if ( v11 >= 0 )
  {
LABEL_21:
    v15 = (const unsigned __int16 *)v10;
    if ( *(_WORD *)v10 )
    {
      while ( 1 )
      {
        pitem = 0;
        v24 = 4;
        v27 = 1;
        v25 = 0;
        v26 = 0;
        v11 = ColorDataController::FillProfile(v12, v15, (struct Profile *)&pitem);
        if ( v11 < 0 )
          break;
        if ( a5 )
        {
          v16 = HIDWORD(v27);
          if ( *a5 == 1 )
            v16 = 1;
          HIDWORD(v27) = v16;
        }
        if ( !*a6 || DSA_InsertItem(*a6, 0x7FFFFFFF, &pitem) == -1 )
          goto LABEL_37;
        v17 = v15;
        v18 = 0x7FFFFFFF;
        do
        {
          if ( !*v17 )
            break;
          ++v17;
          --v18;
        }
        while ( v18 );
        v12 = (ColorDataController *)(0x7FFFFFFF - v18);
        v11 = v18 == 0 ? 0x80070057 : 0;
        if ( v18 )
        {
          v15 += ((0x7FFFFFFF - v18) & -(__int64)(v18 != 0)) + 1;
          if ( *v15 )
            continue;
        }
        break;
      }
    }
  }
LABEL_38:
  operator delete[](v10);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180011050  mov     [rsp-8+arg_0], rbx
0x180011055  push    rbp
0x180011056  push    rsi
0x180011057  push    rdi
0x180011058  push    r12
0x18001105a  push    r13
0x18001105c  push    r14
0x18001105e  push    r15
0x180011060  lea     rbp, [rsp-3E0h]
0x180011068  sub     rsp, 4E0h
0x18001106f  mov     rax, cs:__security_cookie
0x180011076  xor     rax, rsp
0x180011079  mov     [rbp+410h+var_40], rax
0x180011080  mov     r15, [rbp+410h+arg_28]
0x180011087  lea     rcx, [rsp+510h+pEnumRecord.dwFields]; void *
0x18001108c  mov     esi, edx
0x18001108e  mov     rdi, r8
0x180011091  xor     edx, edx; Val
0x180011093  mov     ebx, r9d
0x180011096  lea     r8d, [rdx+58h]; Size
0x18001109a  call    memset_0
0x18001109f  mov     r14, [rbp+410h+arg_20]
0x1800110a6  xor     r12d, r12d
0x1800110a9  mov     [rsp+510h+pdwSize], r12d
0x1800110ae  mov     eax, r12d
0x1800110b1  mov     [rsp+510h+var_4DC], r12d
0x1800110b6  mov     [rsp+510h+pEnumRecord.dwSize], 60h ; '`'
0x1800110be  mov     [rsp+510h+pEnumRecord.dwVersion], 300h
0x1800110c6  lea     r13d, [r12+1]
0x1800110cb  test    rdi, rdi
0x1800110ce  jz      short loc_1800110F7
0x1800110d0  mov     [rsp+510h+pEnumRecord.dwFields], r13d
0x1800110d5  mov     eax, r13d
0x1800110d8  mov     [rsp+510h+pEnumRecord.pDeviceName], rdi
0x1800110dd  test    r14, r14
0x1800110e0  jz      short loc_1800110F7
0x1800110e2  mov     eax, [r14]
0x1800110e5  neg     eax
0x1800110e7  sbb     eax, eax
0x1800110e9  and     eax, 20000h
0x1800110ee  add     eax, 20001h
0x1800110f3  mov     [rsp+510h+pEnumRecord.dwFields], eax
0x1800110f7  test    ebx, ebx
0x1800110f9  jz      short loc_180011106
0x1800110fb  bts     eax, 10h
0x1800110ff  mov     [rbp+410h+pEnumRecord.dwDeviceClass], ebx
0x180011102  mov     [rsp+510h+pEnumRecord.dwFields], eax
0x180011106  mov     ecx, 0A00h; unsigned __int64
0x18001110b  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180011110  mov     rdi, rax
0x180011113  test    rax, rax
0x180011116  jnz     short loc_180011122
0x180011118  mov     ebx, 8007000Eh
0x18001111d  jmp     loc_1800112DC
0x180011122  lea     rax, [rsp+510h+var_4DC]
0x180011127  mov     r9d, 0A00h; dwSize
0x18001112d  mov     r8, rdi; pBuffer
0x180011130  mov     [rsp+510h+pnProfiles], rax; pnProfiles
0x180011135  lea     rdx, [rsp+510h+pEnumRecord]; pEnumRecord
0x18001113a  mov     ecx, esi; scope
0x18001113c  mov     ebx, r12d
0x18001113f  call    cs:__imp_WcsEnumColorProfiles
0x180011145  test    eax, eax
0x180011147  jnz     loc_180011204
0x18001114d  call    cs:__imp_GetLastError
0x180011153  cmp     eax, 7Ah ; 'z'
0x180011156  jnz     loc_1800112CB
0x18001115c  lea     r8, [rsp+510h+pdwSize]; pdwSize
0x180011161  mov     ecx, esi; scope
0x180011163  lea     rdx, [rsp+510h+pEnumRecord]; pEnumRecord
0x180011168  call    cs:__imp_WcsEnumColorProfilesSize
0x18001116e  test    eax, eax
0x180011170  jnz     short loc_180011196
0x180011172  call    cs:__imp_GetLastError
0x180011178  mov     ebx, eax
0x18001117a  test    eax, eax
0x18001117c  jz      loc_1800112D7
0x180011182  jle     loc_1800112DC
0x180011188  movzx   ebx, ax
0x18001118b  or      ebx, 80070000h
0x180011191  jmp     loc_1800112DC
0x180011196  cmp     [rsp+510h+pdwSize], r12d
0x18001119b  jz      loc_1800112DC
0x1800111a1  mov     rcx, rdi; Block
0x1800111a4  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x1800111a9  mov     ecx, [rsp+510h+pdwSize]; unsigned __int64
0x1800111ad  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800111b2  mov     rdi, rax
0x1800111b5  test    rax, rax
0x1800111b8  jz      loc_180011118
0x1800111be  mov     r9d, [rsp+510h+pdwSize]; dwSize
0x1800111c3  lea     rax, [rsp+510h+var_4DC]
0x1800111c8  mov     r8, rdi; pBuffer
0x1800111cb  mov     [rsp+510h+pnProfiles], rax; pnProfiles
0x1800111d0  lea     rdx, [rsp+510h+pEnumRecord]; pEnumRecord
0x1800111d5  mov     ecx, esi; scope
0x1800111d7  call    cs:__imp_WcsEnumColorProfiles
0x1800111dd  test    eax, eax
0x1800111df  jnz     short loc_180011204
0x1800111e1  call    cs:__imp_GetLastError
0x1800111e7  mov     ebx, eax
0x1800111e9  test    eax, eax
0x1800111eb  jz      loc_1800112D7
0x1800111f1  jle     short loc_1800111FC
0x1800111f3  movzx   ebx, ax
0x1800111f6  or      ebx, 80070000h
0x1800111fc  test    ebx, ebx
0x1800111fe  js      loc_1800112DC
0x180011204  mov     rsi, rdi
0x180011207  cmp     [rdi], r12w
0x18001120b  jz      loc_1800112DC
0x180011211  lea     r8, [rbp+410h+pitem]; struct Profile *
0x180011215  mov     [rbp+410h+pitem], r12d
0x180011219  mov     rdx, rsi; unsigned __int16 *
0x18001121c  mov     [rbp+410h+var_46C], 4
0x180011224  mov     [rbp+410h+var_54], r13
0x18001122b  mov     [rbp+410h+var_464], r12w
0x180011230  mov     [rbp+410h+var_25C], r12w
0x180011238  call    ?FillProfile@ColorDataController@@QEBAJPEBGPEAUProfile@@@Z; ColorDataController::FillProfile(ushort const *,Profile *)
0x18001123d  mov     ebx, eax
0x18001123f  test    eax, eax
0x180011241  js      loc_1800112DC
0x180011247  test    r14, r14
0x18001124a  jz      short loc_18001125F
0x18001124c  mov     eax, dword ptr [rbp+410h+var_54+4]
0x180011252  cmp     [r14], r13d
0x180011255  cmovz   eax, r13d
0x180011259  mov     dword ptr [rbp+410h+var_54+4], eax
0x18001125f  mov     rcx, [r15]; hdsa
0x180011262  test    rcx, rcx
0x180011265  jz      short loc_1800112D7
0x180011267  lea     r8, [rbp+410h+pitem]; pitem
0x18001126b  mov     edx, 7FFFFFFFh; i
0x180011270  call    DSA_InsertItem
0x180011275  cmp     eax, 0FFFFFFFFh
0x180011278  jz      short loc_1800112D7
0x18001127a  mov     ecx, 7FFFFFFFh
0x18001127f  mov     rax, rsi
0x180011282  mov     edx, ecx
0x180011284  cmp     [rax], r12w
0x180011288  jz      short loc_180011293
0x18001128a  add     rax, 2
0x18001128e  sub     rdx, r13
0x180011291  jnz     short loc_180011284
0x180011293  mov     rax, rdx
0x180011296  neg     rax
0x180011299  mov     rax, rdx
0x18001129c  sbb     ebx, ebx
0x18001129e  sub     rcx, rdx
0x1800112a1  not     ebx
0x1800112a3  and     ebx, 80070057h
0x1800112a9  neg     rax
0x1800112ac  sbb     r8, r8
0x1800112af  and     r8, rcx
0x1800112b2  test    rdx, rdx
0x1800112b5  jz      short loc_1800112DC
0x1800112b7  lea     rsi, [rsi+r8*2]
0x1800112bb  add     rsi, 2
0x1800112bf  cmp     [rsi], r12w
0x1800112c3  jnz     loc_180011211
0x1800112c9  jmp     short loc_1800112DC
0x1800112cb  test    eax, eax
0x1800112cd  jg      loc_180011188
0x1800112d3  mov     ebx, eax
0x1800112d5  jmp     short loc_1800112DC
0x1800112d7  mov     ebx, 80004005h
0x1800112dc  mov     rcx, rdi; Block
0x1800112df  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x1800112e4  mov     eax, ebx
0x1800112e6  mov     rcx, [rbp+410h+var_40]
0x1800112ed  xor     rcx, rsp; StackCookie
0x1800112f0  call    __security_check_cookie
0x1800112f5  mov     rbx, [rsp+510h+arg_0]
0x1800112fd  add     rsp, 4E0h
0x180011304  pop     r15
0x180011306  pop     r14
0x180011308  pop     r13
0x18001130a  pop     r12
0x18001130c  pop     rdi
0x18001130d  pop     rsi
0x18001130e  pop     rbp
0x18001130f  retn
```
