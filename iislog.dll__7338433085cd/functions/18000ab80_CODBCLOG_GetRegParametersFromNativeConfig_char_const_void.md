# CODBCLOG::GetRegParametersFromNativeConfig(char const *,void *)

- ea: `0x18000ab80`
- end: `0x18000af9f`
- name: `?GetRegParametersFromNativeConfig@CODBCLOG@@QEAAKPEBDPEAX@Z`
- size: `1055`
- prototype: `__int64 __fastcall(CODBCLOG *this, const char *, __int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000afb0`

## callees

- `0x18000ab80`
- `0x18000eca0`
- `0x180010010`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x18000acb7`
- `msvcrt!wcscpy_s` at `0x18000acb7`
- `msvcrt!wcsncat_s` at `0x18000accf`
- `msvcrt!wcsncat_s` at `0x18000accf`
- `msvcrt!atol` at `0x18000abe4`
- `msvcrt!atol` at `0x18000abe4`

## pseudocode

```c
__int64 __fastcall CODBCLOG::GetRegParametersFromNativeConfig(
        CODBCLOG *this,
        const char *a2,
        __int64 (__fastcall ***a3)(_QWORD, GUID *, __int64 *))
{
  unsigned int v5; // edi
  int v6; // ebx
  __int64 v7; // rcx
  unsigned __int64 v8; // rsi
  char *v9; // rcx
  unsigned __int64 v10; // rax
  unsigned int v11; // r8d
  _BYTE *v12; // rdx
  char v13; // al
  char *v14; // rcx
  unsigned __int64 v15; // rax
  unsigned int v16; // r8d
  _BYTE *v17; // rdx
  char v18; // al
  char *v19; // rcx
  unsigned __int64 v20; // rax
  unsigned int v21; // edi
  unsigned int v22; // r8d
  _BYTE *v23; // rdx
  char v24; // al
  char *v25; // rcx
  _BYTE *v26; // rdx
  char v27; // al
  __int64 result; // rax
  __int64 v29; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v30; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v31; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v32; // [rsp+58h] [rbp-A8h] BYREF
  wchar_t *Source; // [rsp+60h] [rbp-A0h] BYREF
  char *v34; // [rsp+68h] [rbp-98h] BYREF
  char *v35; // [rsp+70h] [rbp-90h] BYREF
  char *v36; // [rsp+78h] [rbp-88h] BYREF
  char *v37; // [rsp+80h] [rbp-80h] BYREF
  wchar_t Destination[256]; // [rsp+90h] [rbp-70h] BYREF

  v32 = 0;
  v30 = 0;
  v29 = 0;
  v31 = 0;
  Source = 0;
  v34 = 0;
  v35 = 0;
  v36 = 0;
  v37 = 0;
  v5 = atol(a2 + 5);
  v6 = (**a3)(a3, &IID_INativeConfigurationSystem, &v32);
  if ( v6 < 0 || (v6 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v32 + 56LL))(v32, &v30), v6 < 0) )
  {
LABEL_43:
    v7 = v30;
    goto LABEL_44;
  }
  v6 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *, _QWORD))(*(_QWORD *)v30 + 32LL))(v30, v5, &v31, 0);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
  v7 = 0;
  v30 = 0;
  if ( v6 >= 0 )
  {
    v6 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, wchar_t **, _QWORD, _QWORD))(*(_QWORD *)v31 + 64LL))(
           v31,
           L"name",
           &Source,
           0,
           0);
    if ( v6 >= 0 )
    {
      Destination[255] = 0;
      wcscpy_s(Destination, 0x100u, L"MACHINE/WEBROOT/APPHOST/");
      v8 = -1;
      wcsncat_s(Destination, 0x100u, Source, 0xFFFFFFFFFFFFFFFFuLL);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
      v31 = 0;
      v6 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, wchar_t *, __int64 *, _QWORD, _QWORD))(*(_QWORD *)v32 + 24LL))(
             v32,
             L"system.webServer/odbcLogging",
             Destination,
             &v29,
             0,
             0);
      if ( v6 >= 0 )
      {
        v6 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, char **, _QWORD, _QWORD))(*(_QWORD *)v29 + 64LL))(
               v29,
               L"dataSource",
               &v34,
               0,
               0);
        if ( v6 >= 0 )
        {
          v9 = v34;
          v10 = -1;
          do
            ++v10;
          while ( *(_WORD *)&v34[2 * v10] );
          v11 = 260;
          if ( v10 < 0x104 )
          {
            v12 = (char *)this + 96;
            while ( *(_WORD *)v9 && v11 > 1 )
            {
              v13 = *v9;
              v9 += 2;
              *v12++ = v13;
              --v11;
            }
            *v12 = 0;
          }
          v6 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, char **, _QWORD, _QWORD))(*(_QWORD *)v29 + 64LL))(
                 v29,
                 L"tableName",
                 &v35,
                 0,
                 0);
          if ( v6 >= 0 )
          {
            v14 = v35;
            v15 = -1;
            do
              ++v15;
            while ( *(_WORD *)&v35[2 * v15] );
            v16 = 30;
            if ( v15 < 0x1E )
            {
              v17 = (char *)this + 356;
              while ( *(_WORD *)v14 && v16 > 1 )
              {
                v18 = *v14;
                v14 += 2;
                *v17++ = v18;
                --v16;
              }
              *v17 = 0;
            }
            v6 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, char **, _QWORD, _QWORD))(*(_QWORD *)v29 + 64LL))(
                   v29,
                   L"userName",
                   &v36,
                   0,
                   0);
            if ( v6 >= 0 )
            {
              v19 = v36;
              v20 = -1;
              do
                ++v20;
              while ( *(_WORD *)&v36[2 * v20] );
              v21 = 257;
              if ( v20 < 0x101 )
              {
                v22 = 257;
                v23 = (char *)this + 386;
                while ( *(_WORD *)v19 && v22 > 1 )
                {
                  v24 = *v19;
                  v19 += 2;
                  *v23++ = v24;
                  --v22;
                }
                *v23 = 0;
              }
              v6 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, char **, _QWORD, _QWORD))(*(_QWORD *)v29 + 64LL))(
                     v29,
                     L"password",
                     &v37,
                     0,
                     0);
              if ( v6 >= 0 )
              {
                v25 = v37;
                do
                  ++v8;
                while ( *(_WORD *)&v37[2 * v8] );
                if ( v8 < 0x101 )
                {
                  v26 = (char *)this + 643;
                  while ( *(_WORD *)v25 && v21 > 1 )
                  {
                    v27 = *v25;
                    v25 += 2;
                    *v26++ = v27;
                    --v21;
                  }
                  *v26 = 0;
                }
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
                return 0;
              }
            }
          }
        }
      }
    }
    goto LABEL_43;
  }
LABEL_44:
  if ( v29 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
    v7 = v30;
    v29 = 0;
  }
  if ( v31 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
    v7 = v30;
    v31 = 0;
  }
  if ( v7 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    v30 = 0;
  }
  if ( v32 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
  result = (unsigned __int16)v6;
  if ( (v6 & 0x1FFF0000) != 0x70000 )
    return (unsigned int)v6;
  return result;
}

```

## disassembly

```asm
0x18000ab80  push    rbp
0x18000ab82  push    rbx
0x18000ab83  push    rsi
0x18000ab84  push    rdi
0x18000ab85  push    r12
0x18000ab87  push    r14
0x18000ab89  push    r15
0x18000ab8b  lea     rbp, [rsp-1A0h]
0x18000ab93  sub     rsp, 2A0h
0x18000ab9a  mov     rax, cs:__security_cookie
0x18000aba1  xor     rax, rsp
0x18000aba4  mov     [rbp+1D0h+var_40], rax
0x18000abab  xor     r15d, r15d
0x18000abae  mov     r14, rcx
0x18000abb1  lea     rcx, [rdx+5]; String
0x18000abb5  mov     [rsp+2D0h+var_278], r15
0x18000abba  mov     [rsp+2D0h+var_288], r15
0x18000abbf  mov     rbx, r8
0x18000abc2  mov     [rsp+2D0h+var_290], r15
0x18000abc7  mov     [rsp+2D0h+var_280], r15
0x18000abcc  mov     [rsp+2D0h+Source], r15
0x18000abd1  mov     [rsp+2D0h+var_268], r15
0x18000abd6  mov     [rsp+2D0h+var_260], r15
0x18000abdb  mov     [rsp+2D0h+var_258], r15
0x18000abe0  mov     [rbp+1D0h+var_250], r15
0x18000abe4  call    cs:__imp_atol
0x18000abea  mov     rdx, [rbx]
0x18000abed  lea     r8, [rsp+2D0h+var_278]
0x18000abf2  mov     edi, eax
0x18000abf4  mov     rcx, rbx
0x18000abf7  mov     rax, [rdx]
0x18000abfa  lea     rdx, IID_INativeConfigurationSystem
0x18000ac01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ac06  mov     ebx, eax
0x18000ac08  test    eax, eax
0x18000ac0a  js      loc_18000AEF3
0x18000ac10  mov     rcx, [rsp+2D0h+var_278]
0x18000ac15  mov     rdx, [rcx]
0x18000ac18  mov     rax, [rdx+38h]
0x18000ac1c  lea     rdx, [rsp+2D0h+var_288]
0x18000ac21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ac26  mov     ebx, eax
0x18000ac28  test    eax, eax
0x18000ac2a  js      loc_18000AEF3
0x18000ac30  mov     rcx, [rsp+2D0h+var_288]
0x18000ac35  lea     r8, [rsp+2D0h+var_280]
0x18000ac3a  xor     r9d, r9d
0x18000ac3d  mov     edx, edi
0x18000ac3f  mov     rax, [rcx]
0x18000ac42  mov     rax, [rax+20h]
0x18000ac46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ac4b  mov     rcx, [rsp+2D0h+var_288]
0x18000ac50  mov     ebx, eax
0x18000ac52  mov     rax, [rcx]
0x18000ac55  mov     rax, [rax+10h]
0x18000ac59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ac5e  mov     ecx, r15d
0x18000ac61  mov     [rsp+2D0h+var_288], rcx
0x18000ac66  test    ebx, ebx
0x18000ac68  js      loc_18000AEF8
0x18000ac6e  mov     rcx, [rsp+2D0h+var_280]
0x18000ac73  lea     r8, [rsp+2D0h+Source]
0x18000ac78  xor     r9d, r9d
0x18000ac7b  mov     [rsp+2D0h+var_2B0], r15
0x18000ac80  lea     rdx, aName; "name"
0x18000ac87  mov     rax, [rcx]
0x18000ac8a  mov     rax, [rax+40h]
0x18000ac8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ac93  mov     ebx, eax
0x18000ac95  test    eax, eax
0x18000ac97  js      loc_18000AEF3
0x18000ac9d  mov     ebx, 100h
0x18000aca2  mov     [rbp+1D0h+var_42], r15w
0x18000acaa  mov     edx, ebx; SizeInWords
0x18000acac  lea     r8, aMachineWebroot; "MACHINE/WEBROOT/APPHOST/"
0x18000acb3  lea     rcx, [rbp+1D0h+Destination]; Destination
0x18000acb7  call    cs:__imp_wcscpy_s
0x18000acbd  mov     r8, [rsp+2D0h+Source]; Source
0x18000acc2  lea     rcx, [rbp+1D0h+Destination]; Destination
0x18000acc6  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000acca  mov     edx, ebx; SizeInWords
0x18000accc  mov     r9, rsi; MaxCount
0x18000accf  call    cs:__imp_wcsncat_s
0x18000acd5  mov     rcx, [rsp+2D0h+var_280]
0x18000acda  mov     rax, [rcx]
0x18000acdd  mov     rax, [rax+10h]
0x18000ace1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ace6  mov     rcx, [rsp+2D0h+var_278]
0x18000aceb  lea     r9, [rsp+2D0h+var_290]
0x18000acf0  mov     [rsp+2D0h+var_280], r15
0x18000acf5  lea     r8, [rbp+1D0h+Destination]
0x18000acf9  mov     [rsp+2D0h+var_2A8], r15
0x18000acfe  lea     rdx, aSystemWebserve; "system.webServer/odbcLogging"
0x18000ad05  mov     [rsp+2D0h+var_2B0], r15
0x18000ad0a  mov     rax, [rcx]
0x18000ad0d  mov     rax, [rax+18h]
0x18000ad11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad16  mov     ebx, eax
0x18000ad18  test    eax, eax
0x18000ad1a  js      loc_18000AEF3
0x18000ad20  mov     rcx, [rsp+2D0h+var_290]
0x18000ad25  lea     r8, [rsp+2D0h+var_268]
0x18000ad2a  xor     r9d, r9d
0x18000ad2d  mov     [rsp+2D0h+var_2B0], r15
0x18000ad32  lea     rdx, aDatasource; "dataSource"
0x18000ad39  mov     rax, [rcx]
0x18000ad3c  mov     rax, [rax+40h]
0x18000ad40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad45  mov     ebx, eax
0x18000ad47  test    eax, eax
0x18000ad49  js      loc_18000AEF3
0x18000ad4f  mov     rcx, [rsp+2D0h+var_268]
0x18000ad54  mov     rax, rsi
0x18000ad57  inc     rax
0x18000ad5a  cmp     [rcx+rax*2], r15w
0x18000ad5f  jnz     short loc_18000AD57
0x18000ad61  or      r12d, 0FFFFFFFFh
0x18000ad65  mov     r8d, 104h
0x18000ad6b  cmp     rax, r8
0x18000ad6e  jnb     short loc_18000AD93
0x18000ad70  lea     rdx, [r14+60h]
0x18000ad74  jmp     short loc_18000AD8A
0x18000ad76  cmp     r8d, 1
0x18000ad7a  jbe     short loc_18000AD90
0x18000ad7c  mov     al, [rcx]
0x18000ad7e  add     rcx, 2
0x18000ad82  mov     [rdx], al
0x18000ad84  inc     rdx
0x18000ad87  add     r8d, r12d
0x18000ad8a  cmp     [rcx], r15w
0x18000ad8e  jnz     short loc_18000AD76
0x18000ad90  mov     [rdx], r15b
0x18000ad93  mov     rcx, [rsp+2D0h+var_290]
0x18000ad98  lea     r8, [rsp+2D0h+var_260]
0x18000ad9d  xor     r9d, r9d
0x18000ada0  mov     [rsp+2D0h+var_2B0], r15
0x18000ada5  lea     rdx, aTablename; "tableName"
0x18000adac  mov     rax, [rcx]
0x18000adaf  mov     rax, [rax+40h]
0x18000adb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000adb8  mov     ebx, eax
0x18000adba  test    eax, eax
0x18000adbc  js      loc_18000AEF3
0x18000adc2  mov     rcx, [rsp+2D0h+var_260]
0x18000adc7  mov     rax, rsi
0x18000adca  inc     rax
0x18000adcd  cmp     [rcx+rax*2], r15w
0x18000add2  jnz     short loc_18000ADCA
0x18000add4  mov     r8d, 1Eh
0x18000adda  cmp     rax, r8
0x18000addd  jnb     short loc_18000AE05
0x18000addf  lea     rdx, [r14+164h]
0x18000ade6  jmp     short loc_18000ADFC
0x18000ade8  cmp     r8d, 1
0x18000adec  jbe     short loc_18000AE02
0x18000adee  mov     al, [rcx]
0x18000adf0  add     rcx, 2
0x18000adf4  mov     [rdx], al
0x18000adf6  inc     rdx
0x18000adf9  add     r8d, r12d
0x18000adfc  cmp     [rcx], r15w
0x18000ae00  jnz     short loc_18000ADE8
0x18000ae02  mov     [rdx], r15b
0x18000ae05  mov     rcx, [rsp+2D0h+var_290]
0x18000ae0a  lea     r8, [rsp+2D0h+var_258]
0x18000ae0f  xor     r9d, r9d
0x18000ae12  mov     [rsp+2D0h+var_2B0], r15
0x18000ae17  lea     rdx, aUsername_0; "userName"
0x18000ae1e  mov     rax, [rcx]
0x18000ae21  mov     rax, [rax+40h]
0x18000ae25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae2a  mov     ebx, eax
0x18000ae2c  test    eax, eax
0x18000ae2e  js      loc_18000AEF3
0x18000ae34  mov     rcx, [rsp+2D0h+var_258]
0x18000ae39  mov     rax, rsi
0x18000ae3c  inc     rax
0x18000ae3f  cmp     [rcx+rax*2], r15w
0x18000ae44  jnz     short loc_18000AE3C
0x18000ae46  mov     edi, 101h
0x18000ae4b  cmp     rax, rdi
0x18000ae4e  jnb     short loc_18000AE79
0x18000ae50  mov     r8d, edi
0x18000ae53  lea     rdx, [r14+182h]
0x18000ae5a  jmp     short loc_18000AE70
0x18000ae5c  cmp     r8d, 1
0x18000ae60  jbe     short loc_18000AE76
0x18000ae62  mov     al, [rcx]
0x18000ae64  add     rcx, 2
0x18000ae68  mov     [rdx], al
0x18000ae6a  inc     rdx
0x18000ae6d  add     r8d, r12d
0x18000ae70  cmp     [rcx], r15w
0x18000ae74  jnz     short loc_18000AE5C
0x18000ae76  mov     [rdx], r15b
0x18000ae79  mov     rcx, [rsp+2D0h+var_290]
0x18000ae7e  lea     r8, [rbp+1D0h+var_250]
0x18000ae82  xor     r9d, r9d
0x18000ae85  mov     [rsp+2D0h+var_2B0], r15
0x18000ae8a  lea     rdx, aPassword; "password"
0x18000ae91  mov     rax, [rcx]
0x18000ae94  mov     rax, [rax+40h]
0x18000ae98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae9d  mov     ebx, eax
0x18000ae9f  test    eax, eax
0x18000aea1  js      short loc_18000AEF3
0x18000aea3  mov     rcx, [rbp+1D0h+var_250]
0x18000aea7  inc     rsi
0x18000aeaa  cmp     [rcx+rsi*2], r15w
0x18000aeaf  jnz     short loc_18000AEA7
0x18000aeb1  cmp     rsi, rdi
0x18000aeb4  jnb     short loc_18000AEDB
0x18000aeb6  lea     rdx, [r14+283h]
0x18000aebd  jmp     short loc_18000AED2
0x18000aebf  cmp     edi, 1
0x18000aec2  jbe     short loc_18000AED8
0x18000aec4  mov     al, [rcx]
0x18000aec6  add     rcx, 2
0x18000aeca  mov     [rdx], al
0x18000aecc  inc     rdx
0x18000aecf  add     edi, r12d
0x18000aed2  cmp     [rcx], r15w
0x18000aed6  jnz     short loc_18000AEBF
0x18000aed8  mov     [rdx], r15b
0x18000aedb  mov     rcx, [rsp+2D0h+var_290]
0x18000aee0  mov     rax, [rcx]
0x18000aee3  mov     rax, [rax+10h]
0x18000aee7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aeec  xor     eax, eax
0x18000aeee  jmp     loc_18000AF7E
0x18000aef3  mov     rcx, [rsp+2D0h+var_288]
0x18000aef8  mov     rdx, [rsp+2D0h+var_290]
0x18000aefd  test    rdx, rdx
0x18000af00  jz      short loc_18000AF1B
0x18000af02  mov     rax, [rdx]
0x18000af05  mov     rcx, rdx
0x18000af08  mov     rax, [rax+10h]
0x18000af0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af11  mov     rcx, [rsp+2D0h+var_288]
0x18000af16  mov     [rsp+2D0h+var_290], r15
0x18000af1b  mov     rdx, [rsp+2D0h+var_280]
0x18000af20  test    rdx, rdx
0x18000af23  jz      short loc_18000AF3E
0x18000af25  mov     rax, [rdx]
0x18000af28  mov     rcx, rdx
0x18000af2b  mov     rax, [rax+10h]
0x18000af2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af34  mov     rcx, [rsp+2D0h+var_288]
0x18000af39  mov     [rsp+2D0h+var_280], r15
0x18000af3e  test    rcx, rcx
0x18000af41  jz      short loc_18000AF54
0x18000af43  mov     rax, [rcx]
0x18000af46  mov     rax, [rax+10h]
0x18000af4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af4f  mov     [rsp+2D0h+var_288], r15
0x18000af54  mov     rcx, [rsp+2D0h+var_278]
0x18000af59  test    rcx, rcx
0x18000af5c  jz      short loc_18000AF6A
0x18000af5e  mov     rax, [rcx]
0x18000af61  mov     rax, [rax+10h]
0x18000af65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af6a  mov     ecx, ebx
0x18000af6c  movzx   eax, bx
0x18000af6f  and     ecx, 1FFF0000h
0x18000af75  cmp     ecx, 70000h
0x18000af7b  cmovnz  eax, ebx
0x18000af7e  mov     rcx, [rbp+1D0h+var_40]
0x18000af85  xor     rcx, rsp; StackCookie
0x18000af88  call    __security_check_cookie
0x18000af8d  add     rsp, 2A0h
0x18000af94  pop     r15
0x18000af96  pop     r14
0x18000af98  pop     r12
0x18000af9a  pop     rdi
0x18000af9b  pop     rsi
0x18000af9c  pop     rbx
0x18000af9d  pop     rbp
0x18000af9e  retn
```
