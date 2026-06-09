# CImpICommandWithParameters::MapParameterNames(ulong,ushort const * * const,long * const)

- ea: `0x10011380`
- end: `0x1001151e`
- name: `?MapParameterNames@CImpICommandWithParameters@@UAGJKQAPBGQAJ@Z`
- size: `414`
- prototype: `int(CImpICommandWithParameters *__hidden this, unsigned int, const unsigned __int16 **const, int *const)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1000ba90`
- `0x10011380`
- `0x1001c380`
- `0x1004d406`
- `0x1004d420`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x10011463`
- `msvcrt!_wcsicmp` at `0x10011463`
- `KERNEL32!LeaveCriticalSection` at `0x10011502`
- `KERNEL32!LeaveCriticalSection` at `0x10011502`
- `KERNEL32!EnterCriticalSection` at `0x100113c7`
- `KERNEL32!EnterCriticalSection` at `0x100113c7`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x100113ae`
- `OLEAUT32!__imp__SetErrorInfo@8` at `0x100113ae`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x100114e6`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x100114e6`

## pseudocode

```c
int __stdcall CImpICommandWithParameters::MapParameterNames(
        CImpICommandWithParameters *this,
        unsigned int a2,
        const unsigned __int16 **const a3,
        int *const a4)
{
  int v4; // edi
  struct _RTL_CRITICAL_SECTION *v5; // esi
  const unsigned __int16 **v6; // ebx
  int *v7; // edi
  int v8; // eax
  unsigned int v9; // eax
  int *v10; // esi
  const wchar_t *v11; // ebx
  int *v12; // ecx
  int *v13; // edi
  const wchar_t *v14; // eax
  int v15; // ecx
  int v16; // edx
  const struct _GUID *v18; // [esp+0h] [ebp-34h]
  int v19; // [esp+4h] [ebp-30h]
  LPCRITICAL_SECTION v20; // [esp+14h] [ebp-20h] BYREF
  int *v21; // [esp+18h] [ebp-1Ch]
  int v22; // [esp+1Ch] [ebp-18h]
  int v23; // [esp+20h] [ebp-14h]
  unsigned int v24; // [esp+24h] [ebp-10h]
  int v25; // [esp+30h] [ebp-4h]

  v4 = 0;
  SetErrorInfo(0, 0);
  v20 = (LPCRITICAL_SECTION)(*((_DWORD *)this + 2) + 248);
  v5 = v20;
  EnterCriticalSection(v20);
  v25 = 0;
  if ( a2 )
  {
    v6 = a3;
    if ( a3 && (v7 = a4) != 0 )
    {
      v21 = (int *)*((_DWORD *)this + 2);
      v8 = v21[15];
      if ( (v8 & 0x20) != 0 )
      {
        if ( (v8 & 0x10) != 0 )
        {
          v9 = 0;
          v23 = 0;
          v22 = 0;
          v24 = 0;
          v10 = v21;
          do
          {
            v11 = v6[v9];
            v12 = &v7[v9];
            *v12 = 0;
            v13 = (int *)v10[21];
            v21 = v12;
            if ( v13 )
            {
              while ( 1 )
              {
                v14 = (const wchar_t *)v13[1];
                if ( v14 )
                {
                  if ( v11 && !__wcsicmp(v14, v11) )
                    break;
                }
                v13 = (int *)v13[10];
                if ( !v13 )
                {
                  v9 = v24;
                  goto LABEL_16;
                }
              }
              v16 = v23;
              *v21 = *v13;
              v15 = 1;
              v9 = v24;
              v22 = 1;
            }
            else
            {
LABEL_16:
              v15 = v22;
              v16 = 1;
              v23 = 1;
            }
            v7 = a4;
            ++v9;
            v6 = a3;
            v24 = v9;
          }
          while ( v9 < a2 );
          v5 = v20;
          if ( v16 != 1 )
          {
            v4 = 0;
            goto LABEL_27;
          }
          if ( v15 == 1 )
          {
            v4 = 265946;
            goto LABEL_27;
          }
          v4 = -2147217887;
        }
        else
        {
          v4 = -2147217846;
        }
      }
      else
      {
        v4 = -2147217908;
      }
    }
    else
    {
      v4 = -2147024809;
    }
    if ( !JetGetDatabaseInfo(
            *(_DWORD *)(*(_DWORD *)(*((_DWORD *)this + 2) + 52) + 16),
            *(_DWORD *)(*(_DWORD *)(*((_DWORD *)this + 2) + 52) + 20),
            &v20,
            4,
            3) )
      CExtError::SendHRtoOLEAuto(v4, (__int128 *)&IID_ICommandWithParameters, 0, v18, v19);
  }
LABEL_27:
  if ( v5 )
    LeaveCriticalSection(v5);
  return v4;
}

```

## disassembly

```asm
0x10011380  mov     edi, edi
0x10011382  push    ebp
0x10011383  mov     ebp, esp
0x10011385  push    0FFFFFFFFh
0x10011387  push    offset ?IsObjectAccessAllowed@CImpIObjectAccessControl@@UAGJPAU_SEC_OBJECT@@PAU_EXPLICIT_ACCESS_W@@PAH@Z_SEH
0x1001138c  mov     eax, large fs:0
0x10011392  push    eax
0x10011393  sub     esp, 18h
0x10011396  push    ebx
0x10011397  push    esi
0x10011398  push    edi; int
0x10011399  mov     eax, ___security_cookie
0x1001139e  xor     eax, ebp
0x100113a0  push    eax; struct _GUID *
0x100113a1  lea     eax, [ebp+var_C]
0x100113a4  mov     large fs:0, eax
0x100113aa  xor     edi, edi
0x100113ac  push    edi; perrinfo
0x100113ad  push    edi; dwReserved
0x100113ae  call    ds:__imp__SetErrorInfo@8; SetErrorInfo(x,x)
0x100113b4  mov     esi, [ebp+this]
0x100113b7  mov     esi, [esi+8]
0x100113ba  add     esi, 0F8h
0x100113c0  push    esi; lpCriticalSection
0x100113c1  mov     [ebp+var_20], esi
0x100113c4  mov     [ebp+var_24], esi
0x100113c7  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x100113cd  mov     ecx, [ebp+arg_4]
0x100113d0  mov     [ebp+var_4], edi
0x100113d3  test    ecx, ecx
0x100113d5  jz      loc_100114FD
0x100113db  mov     ebx, [ebp+arg_8]
0x100113de  test    ebx, ebx
0x100113e0  jz      loc_100114CA
0x100113e6  mov     edi, [ebp+arg_C]
0x100113e9  test    edi, edi
0x100113eb  jz      loc_100114CA
0x100113f1  mov     eax, [ebp+this]
0x100113f4  mov     eax, [eax+8]
0x100113f7  mov     [ebp+var_1C], eax
0x100113fa  mov     eax, [eax+3Ch]
0x100113fd  test    al, 20h
0x100113ff  jnz     short loc_1001140B
0x10011401  mov     edi, 80040E0Ch
0x10011406  jmp     loc_100114CF
0x1001140b  test    al, 10h
0x1001140d  jnz     short loc_10011419
0x1001140f  mov     edi, 80040E4Ah
0x10011414  jmp     loc_100114CF
0x10011419  xor     eax, eax
0x1001141b  mov     [ebp+var_14], 0
0x10011422  mov     [ebp+var_18], 0
0x10011429  mov     [ebp+var_10], eax
0x1001142c  test    ecx, ecx
0x1001142e  jz      loc_100114C6
0x10011434  mov     esi, [ebp+var_1C]
0x10011437  nop     word ptr [eax+eax+00000000h]
0x10011440  mov     ebx, [ebx+eax*4]
0x10011443  lea     ecx, [edi+eax*4]
0x10011446  mov     dword ptr [ecx], 0
0x1001144c  mov     edi, [esi+54h]
0x1001144f  mov     [ebp+var_1C], ecx
0x10011452  test    edi, edi
0x10011454  jz      short loc_1001147A
0x10011456  mov     eax, [edi+4]
0x10011459  test    eax, eax
0x1001145b  jz      short loc_10011470
0x1001145d  test    ebx, ebx
0x1001145f  jz      short loc_10011470
0x10011461  push    ebx; String2
0x10011462  push    eax; String1
0x10011463  call    ds:__imp___wcsicmp
0x10011469  add     esp, 8
0x1001146c  test    eax, eax
0x1001146e  jz      short loc_100114A8
0x10011470  mov     edi, [edi+28h]
0x10011473  test    edi, edi
0x10011475  jnz     short loc_10011456
0x10011477  mov     eax, [ebp+var_10]
0x1001147a  mov     ecx, [ebp+var_18]
0x1001147d  mov     edx, 1
0x10011482  mov     [ebp+var_14], edx
0x10011485  mov     edi, [ebp+arg_C]
0x10011488  inc     eax
0x10011489  mov     ebx, [ebp+arg_8]
0x1001148c  mov     [ebp+var_10], eax
0x1001148f  cmp     eax, [ebp+arg_4]
0x10011492  jb      short loc_10011440
0x10011494  mov     esi, [ebp+var_20]
0x10011497  cmp     edx, 1
0x1001149a  jnz     short loc_100114C6
0x1001149c  cmp     ecx, 1
0x1001149f  jnz     short loc_100114BF
0x100114a1  mov     edi, 40EDAh
0x100114a6  jmp     short loc_100114FD
0x100114a8  mov     ecx, [ebp+var_1C]
0x100114ab  mov     eax, [edi]
0x100114ad  mov     edx, [ebp+var_14]
0x100114b0  mov     [ecx], eax
0x100114b2  mov     ecx, 1
0x100114b7  mov     eax, [ebp+var_10]
0x100114ba  mov     [ebp+var_18], ecx
0x100114bd  jmp     short loc_10011485
0x100114bf  mov     edi, 80040E21h
0x100114c4  jmp     short loc_100114CF
0x100114c6  xor     edi, edi
0x100114c8  jmp     short loc_100114FD
0x100114ca  mov     edi, 80070057h
0x100114cf  mov     eax, [ebp+this]
0x100114d2  lea     ecx, [ebp+var_20]
0x100114d5  push    3
0x100114d7  push    4
0x100114d9  push    ecx
0x100114da  mov     eax, [eax+8]
0x100114dd  mov     eax, [eax+34h]
0x100114e0  push    dword ptr [eax+14h]
0x100114e3  push    dword ptr [eax+10h]
0x100114e6  call    ds:__imp__JetGetDatabaseInfo@20; JetGetDatabaseInfo(x,x,x,x,x)
0x100114ec  test    eax, eax
0x100114ee  jnz     short loc_100114FD
0x100114f0  push    eax; int
0x100114f1  push    offset _IID_ICommandWithParameters; int
0x100114f6  mov     edx, edi
0x100114f8  call    ?SendHRtoOLEAuto@CExtError@@SGJJJABU_GUID@@J@Z; CExtError::SendHRtoOLEAuto(long,long,_GUID const &,long)
0x100114fd  test    esi, esi
0x100114ff  jz      short loc_10011508
0x10011501  push    esi; lpCriticalSection
0x10011502  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10011508  mov     eax, edi
0x1001150a  mov     ecx, [ebp+var_C]
0x1001150d  mov     large fs:0, ecx
0x10011514  pop     ecx
0x10011515  pop     edi
0x10011516  pop     esi
0x10011517  pop     ebx
0x10011518  mov     esp, ebp
0x1001151a  pop     ebp
0x1001151b  retn    10h
0x1004dfd0  lea     ecx, [ebp+var_24]; this
0x1004dfd3  jmp     ??1CMutex@@QAE@XZ; CMutex::~CMutex(void)
0x1004dfdd  nop
0x1004dfde  nop
0x1004dfdf  mov     edx, [esp-4+arg_4]
0x1004dfe3  lea     eax, [edx+0Ch]
0x1004dfe6  mov     ecx, [edx-28h]
0x1004dfe9  xor     ecx, eax; StackCookie
0x1004dfeb  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1004dff0  mov     eax, offset stru_1004F550
0x1004dff5  jmp     ___CxxFrameHandler3
```
