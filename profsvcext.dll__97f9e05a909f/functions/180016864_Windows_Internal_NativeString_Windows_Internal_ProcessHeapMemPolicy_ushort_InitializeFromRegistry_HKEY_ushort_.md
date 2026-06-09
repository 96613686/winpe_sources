# Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_InitializeFromRegistry(HKEY__ *,ushort const *,bool)

- ea: `0x180016864`
- end: `0x180016a14`
- name: `?_InitializeFromRegistry@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEAUHKEY__@@PEBG_N@Z`
- size: `432`
- prototype: `__int64 __fastcall(BYTE **, HKEY, const WCHAR *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180013af4`

## callees

- `0x180005424`
- `0x18000ccfc`
- `0x180012d00`
- `0x180016864`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800168af`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180016924`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800168af`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180016924`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180016958`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180016986`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180016958`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180016986`

## pseudocode

```c
__int64 __fastcall Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_InitializeFromRegistry(
        BYTE **a1,
        HKEY a2,
        const WCHAR *a3)
{
  BYTE *lpData; // rdi
  LSTATUS v7; // eax
  signed int v8; // ebx
  LSTATUS v9; // eax
  __int64 v10; // rsi
  DWORD v11; // eax
  DWORD v12; // ebp
  WCHAR *v13; // rax
  BYTE *v14; // rsi
  DWORD v15; // eax
  DWORD v16; // r14d
  __int64 v17; // rax
  DWORD Type[14]; // [rsp+30h] [rbp-38h] BYREF
  DWORD cbData; // [rsp+88h] [rbp+20h] BYREF

  Type[0] = 0;
  cbData = 0;
  lpData = 0;
  v7 = RegQueryValueExW(a2, a3, 0, Type, 0, &cbData);
  v8 = v7;
  if ( v7 > 0 )
    v8 = (unsigned __int16)v7 | 0x80070000;
  if ( v8 >= 0 )
  {
    if ( Type[0] - 1 > 1 || !cbData || (cbData & 1) != 0 )
      goto LABEL_24;
    lpData = (BYTE *)Windows::Internal::ProcessHeapMemPolicy<unsigned short>::Alloc(cbData);
    if ( !lpData )
    {
LABEL_14:
      v8 = -2147024882;
      goto LABEL_25;
    }
    v9 = RegQueryValueExW(a2, a3, 0, Type, lpData, &cbData);
    v8 = v9;
    if ( v9 > 0 )
      v8 = (unsigned __int16)v9 | 0x80070000;
    if ( v8 >= 0 )
    {
      v10 = (cbData >> 1) - 1;
      if ( Type[0] == 2 )
      {
        v11 = ExpandEnvironmentStringsW((LPCWSTR)lpData, 0, 0);
        v12 = v11;
        if ( v11 )
        {
          v13 = (WCHAR *)Windows::Internal::ProcessHeapMemPolicy<unsigned short>::Alloc(2LL * v11);
          v14 = (BYTE *)v13;
          if ( !v13 )
            goto LABEL_14;
          v15 = ExpandEnvironmentStringsW((LPCWSTR)lpData, v13, v12);
          v16 = v15;
          if ( !v15 || v15 > v12 )
          {
            v8 = -2147024774;
            Windows::Internal::ProcessHeapMemPolicy<unsigned short>::Free(v14);
            goto LABEL_25;
          }
          v8 = 0;
          Windows::Internal::ProcessHeapMemPolicy<unsigned short>::Free(lpData);
          lpData = v14;
          v10 = v16 - 1;
        }
      }
      if ( !*(_WORD *)&lpData[2 * v10] )
      {
        Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(a1);
        if ( lpData )
        {
          v17 = (unsigned int)(v10 + 1);
          if ( (_DWORD)v10 != -1 )
          {
            *a1 = lpData;
            a1[1] = (BYTE *)(v17 - 1);
            a1[2] = (BYTE *)(unsigned int)v17;
            *(_WORD *)&lpData[2 * (unsigned int)v17 - 2] = 0;
          }
        }
        lpData = 0;
        goto LABEL_25;
      }
LABEL_24:
      v8 = -2147024883;
    }
  }
LABEL_25:
  Windows::Internal::ProcessHeapMemPolicy<unsigned short>::Free(lpData);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180016864  mov     r11, rsp
0x180016867  mov     [r11+8], rbx
0x18001686b  mov     [r11+10h], rbp
0x18001686f  mov     [r11+20h], r9b
0x180016873  push    rsi
0x180016874  push    rdi
0x180016875  push    r12
0x180016877  push    r14
0x180016879  push    r15
0x18001687b  sub     rsp, 40h
0x18001687f  xor     r12d, r12d
0x180016882  lea     rax, [r11+20h]
0x180016886  mov     rsi, r8
0x180016889  mov     [r11-40h], rax
0x18001688d  mov     rbp, rdx
0x180016890  mov     [r11-48h], r12
0x180016894  mov     r15, rcx
0x180016897  mov     [r11-38h], r12d
0x18001689b  mov     rdx, rsi; lpValueName
0x18001689e  mov     [r11+20h], r12d
0x1800168a2  mov     rcx, rbp; hKey
0x1800168a5  lea     r9, [r11-38h]; lpType
0x1800168a9  xor     r8d, r8d; lpReserved
0x1800168ac  mov     edi, r12d
0x1800168af  call    cs:__imp_RegQueryValueExW
0x1800168b5  mov     ebx, eax
0x1800168b7  mov     r14d, 80070000h
0x1800168bd  test    eax, eax
0x1800168bf  jle     short loc_1800168C7
0x1800168c1  movzx   ebx, ax
0x1800168c4  or      ebx, r14d
0x1800168c7  test    ebx, ebx
0x1800168c9  js      loc_1800169F3
0x1800168cf  mov     eax, [rsp+68h+Type]
0x1800168d3  dec     eax
0x1800168d5  cmp     eax, 1
0x1800168d8  ja      loc_1800169EE
0x1800168de  mov     eax, [rsp+68h+cbData]
0x1800168e5  test    eax, eax
0x1800168e7  jz      loc_1800169EE
0x1800168ed  test    al, 1
0x1800168ef  jnz     loc_1800169EE
0x1800168f5  mov     ecx, eax
0x1800168f7  call    ?Alloc@?$ProcessHeapMemPolicy@G@Internal@Windows@@SAPEAG_K@Z; Windows::Internal::ProcessHeapMemPolicy<ushort>::Alloc(unsigned __int64)
0x1800168fc  mov     rdi, rax
0x1800168ff  test    rax, rax
0x180016902  jz      short loc_180016976
0x180016904  lea     rax, [rsp+68h+cbData]
0x18001690c  xor     r8d, r8d; lpReserved
0x18001690f  mov     [rsp+68h+lpcbData], rax; lpcbData
0x180016914  lea     r9, [rsp+68h+Type]; lpType
0x180016919  mov     rdx, rsi; lpValueName
0x18001691c  mov     [rsp+68h+lpData], rdi; lpData
0x180016921  mov     rcx, rbp; hKey
0x180016924  call    cs:__imp_RegQueryValueExW
0x18001692a  mov     ebx, eax
0x18001692c  test    eax, eax
0x18001692e  jle     short loc_180016936
0x180016930  movzx   ebx, ax
0x180016933  or      ebx, r14d
0x180016936  test    ebx, ebx
0x180016938  js      loc_1800169F3
0x18001693e  mov     esi, [rsp+68h+cbData]
0x180016945  shr     esi, 1
0x180016947  dec     esi
0x180016949  cmp     [rsp+68h+Type], 2
0x18001694e  jnz     short loc_1800169A9
0x180016950  xor     r8d, r8d; nSize
0x180016953  xor     edx, edx; lpDst
0x180016955  mov     rcx, rdi; lpSrc
0x180016958  call    cs:__imp_ExpandEnvironmentStringsW
0x18001695e  mov     ebp, eax
0x180016960  test    eax, eax
0x180016962  jz      short loc_1800169A9
0x180016964  mov     ecx, ebp
0x180016966  add     rcx, rcx
0x180016969  call    ?Alloc@?$ProcessHeapMemPolicy@G@Internal@Windows@@SAPEAG_K@Z; Windows::Internal::ProcessHeapMemPolicy<ushort>::Alloc(unsigned __int64)
0x18001696e  mov     rsi, rax
0x180016971  test    rax, rax
0x180016974  jnz     short loc_18001697D
0x180016976  mov     ebx, 8007000Eh
0x18001697b  jmp     short loc_1800169F3
0x18001697d  mov     r8d, ebp; nSize
0x180016980  mov     rdx, rsi; lpDst
0x180016983  mov     rcx, rdi; lpSrc
0x180016986  call    cs:__imp_ExpandEnvironmentStringsW
0x18001698c  mov     r14d, eax
0x18001698f  test    eax, eax
0x180016991  jz      short loc_1800169DF
0x180016993  cmp     eax, ebp
0x180016995  ja      short loc_1800169DF
0x180016997  mov     rcx, rdi
0x18001699a  mov     ebx, r12d
0x18001699d  call    ?Free@?$ProcessHeapMemPolicy@G@Internal@Windows@@SAXPEAG@Z; Windows::Internal::ProcessHeapMemPolicy<ushort>::Free(ushort *)
0x1800169a2  mov     rdi, rsi
0x1800169a5  lea     esi, [r14-1]
0x1800169a9  cmp     [rdi+rsi*2], r12w
0x1800169ae  jnz     short loc_1800169EE
0x1800169b0  mov     rcx, r15
0x1800169b3  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800169b8  test    rdi, rdi
0x1800169bb  jz      short loc_1800169DA
0x1800169bd  lea     eax, [rsi+1]
0x1800169c0  mov     ecx, eax
0x1800169c2  test    eax, eax
0x1800169c4  jz      short loc_1800169DA
0x1800169c6  dec     rax
0x1800169c9  mov     [r15], rdi
0x1800169cc  mov     [r15+8], rax
0x1800169d0  mov     [r15+10h], rcx
0x1800169d4  mov     [rdi+rcx*2-2], r12w
0x1800169da  mov     rdi, r12
0x1800169dd  jmp     short loc_1800169F3
0x1800169df  mov     rcx, rsi
0x1800169e2  mov     ebx, 8007007Ah
0x1800169e7  call    ?Free@?$ProcessHeapMemPolicy@G@Internal@Windows@@SAXPEAG@Z; Windows::Internal::ProcessHeapMemPolicy<ushort>::Free(ushort *)
0x1800169ec  jmp     short loc_1800169F3
0x1800169ee  mov     ebx, 8007000Dh
0x1800169f3  mov     rcx, rdi
0x1800169f6  call    ?Free@?$ProcessHeapMemPolicy@G@Internal@Windows@@SAXPEAG@Z; Windows::Internal::ProcessHeapMemPolicy<ushort>::Free(ushort *)
0x1800169fb  mov     rbp, [rsp+68h+arg_8]
0x180016a00  mov     eax, ebx
0x180016a02  mov     rbx, [rsp+68h+arg_0]
0x180016a07  add     rsp, 40h
0x180016a0b  pop     r15
0x180016a0d  pop     r14
0x180016a0f  pop     r12
0x180016a11  pop     rdi
0x180016a12  pop     rsi
0x180016a13  retn
```
