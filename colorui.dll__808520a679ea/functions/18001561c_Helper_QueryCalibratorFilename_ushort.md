# Helper::QueryCalibratorFilename(ushort * *)

- ea: `0x18001561c`
- end: `0x18001574b`
- name: `?QueryCalibratorFilename@Helper@@YAHPEAPEAG@Z`
- size: `303`
- prototype: `__int64 __fastcall(Helper *__hidden this, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18000ffe0`
- `0x180012840`

## callees

- `0x180001340`
- `0x18000138c`
- `0x18001561c`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x180015664`
- `ADVAPI32!RegOpenKeyExW` at `0x180015664`
- `ADVAPI32!RegCloseKey` at `0x18001572e`
- `ADVAPI32!RegCloseKey` at `0x18001572e`
- `ADVAPI32!RegQueryValueExW` at `0x180015692`
- `ADVAPI32!RegQueryValueExW` at `0x1800156f5`
- `ADVAPI32!RegQueryValueExW` at `0x180015692`
- `ADVAPI32!RegQueryValueExW` at `0x1800156f5`

## pseudocode

```c
__int64 __fastcall Helper::QueryCalibratorFilename(Helper *this, unsigned __int16 **a2)
{
  unsigned int v2; // esi
  BYTE *v3; // rbx
  DWORD cbData; // [rsp+50h] [rbp+20h] BYREF
  DWORD Type; // [rsp+58h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+60h] [rbp+30h] BYREF

  v2 = 0;
  v3 = 0;
  hKey = 0;
  Type = 0;
  cbData = 0;
  if ( this )
    *(_QWORD *)this = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\ICM\\Calibration",
          0,
          0x20019u,
          &hKey)
    && !RegQueryValueExW(hKey, L"DisplayCalibrator", 0, &Type, 0, &cbData)
    && Type == 1
    && (cbData & 1) == 0 )
  {
    v3 = (BYTE *)operator new[](saturated_mul((unsigned __int64)cbData >> 1, 2u));
    if ( v3 )
    {
      if ( !RegQueryValueExW(hKey, L"DisplayCalibrator", 0, &Type, v3, &cbData)
        && Type == 1
        && cbData > 2
        && !*(_WORD *)&v3[2 * ((unsigned __int64)cbData >> 1) - 2] )
      {
        v2 = 1;
        if ( this )
        {
          *(_QWORD *)this = v3;
          v3 = 0;
        }
      }
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  operator delete[](v3);
  return v2;
}

```

## disassembly

```asm
0x18001561c  mov     [rsp-18h+arg_18], rbx
0x180015621  push    rbp
0x180015622  push    rsi
0x180015623  push    rdi
0x180015624  mov     rbp, rsp
0x180015627  sub     rsp, 30h
0x18001562b  xor     esi, esi
0x18001562d  xor     ebx, ebx
0x18001562f  mov     [rbp+hKey], rsi
0x180015633  mov     rdi, rcx
0x180015636  mov     [rbp+Type], esi
0x180015639  mov     [rbp+cbData], esi
0x18001563c  test    rcx, rcx
0x18001563f  jz      short loc_180015644
0x180015641  mov     [rcx], rbx
0x180015644  lea     rax, [rbp+hKey]
0x180015648  mov     r9d, 20019h; samDesired
0x18001564e  xor     r8d, r8d; ulOptions
0x180015651  mov     [rsp+30h+phkResult], rax; phkResult
0x180015656  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18001565d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180015664  call    cs:__imp_RegOpenKeyExW
0x18001566a  test    eax, eax
0x18001566c  jnz     loc_180015725
0x180015672  mov     rcx, [rbp+hKey]; hKey
0x180015676  lea     rax, [rbp+cbData]
0x18001567a  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18001567f  lea     r9, [rbp+Type]; lpType
0x180015683  xor     r8d, r8d; lpReserved
0x180015686  mov     [rsp+30h+phkResult], rbx; lpData
0x18001568b  lea     rdx, ValueName; "DisplayCalibrator"
0x180015692  call    cs:__imp_RegQueryValueExW
0x180015698  test    eax, eax
0x18001569a  jnz     loc_180015725
0x1800156a0  cmp     [rbp+Type], 1
0x1800156a4  jnz     short loc_180015725
0x1800156a6  test    byte ptr [rbp+cbData], 1
0x1800156aa  jnz     short loc_180015725
0x1800156ac  mov     ecx, [rbp+cbData]
0x1800156af  mov     eax, 2
0x1800156b4  shr     rcx, 1
0x1800156b7  mul     rcx
0x1800156ba  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800156c1  cmovb   rax, rcx
0x1800156c5  mov     rcx, rax; unsigned __int64
0x1800156c8  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800156cd  mov     rbx, rax
0x1800156d0  test    rax, rax
0x1800156d3  jz      short loc_180015725
0x1800156d5  mov     rcx, [rbp+hKey]; hKey
0x1800156d9  lea     rax, [rbp+cbData]
0x1800156dd  mov     [rsp+30h+lpcbData], rax; lpcbData
0x1800156e2  lea     r9, [rbp+Type]; lpType
0x1800156e6  xor     r8d, r8d; lpReserved
0x1800156e9  mov     [rsp+30h+phkResult], rbx; lpData
0x1800156ee  lea     rdx, ValueName; "DisplayCalibrator"
0x1800156f5  call    cs:__imp_RegQueryValueExW
0x1800156fb  test    eax, eax
0x1800156fd  jnz     short loc_180015725
0x1800156ff  cmp     [rbp+Type], 1
0x180015703  jnz     short loc_180015725
0x180015705  cmp     [rbp+cbData], 2
0x180015709  jbe     short loc_180015725
0x18001570b  mov     ecx, [rbp+cbData]
0x18001570e  shr     rcx, 1
0x180015711  cmp     ax, [rbx+rcx*2-2]
0x180015716  jnz     short loc_180015725
0x180015718  lea     esi, [rax+1]
0x18001571b  test    rdi, rdi
0x18001571e  jz      short loc_180015725
0x180015720  mov     [rdi], rbx
0x180015723  xor     ebx, ebx
0x180015725  mov     rcx, [rbp+hKey]; hKey
0x180015729  test    rcx, rcx
0x18001572c  jz      short loc_180015734
0x18001572e  call    cs:__imp_RegCloseKey
0x180015734  mov     rcx, rbx; Block
0x180015737  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x18001573c  mov     rbx, [rsp+30h+arg_18]
0x180015741  mov     eax, esi
0x180015743  add     rsp, 30h
0x180015747  pop     rdi
0x180015748  pop     rsi
0x180015749  pop     rbp
0x18001574a  retn
```
