# RegistryPropertyBag::MetadataCachePathProperty::Read(HKEY__ *)

- ea: `0x18005661c`
- end: `0x1800567da`
- name: `?Read@MetadataCachePathProperty@RegistryPropertyBag@@MEAAJPEAUHKEY__@@@Z`
- size: `446`
- prototype: `__int64 __fastcall(RegistryPropertyBag::MetadataCachePathProperty *__hidden this, HKEY)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180055a10`

## callees

- `0x1800024e0`
- `0x18002d5a4`
- `0x180055448`
- `0x180055470`
- `0x18005661c`
- `0x180056980`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18005674d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18005674d`
- `api-ms-win-crt-private-l1-1-0!_o_isalpha` at `0x1800566ed`
- `api-ms-win-crt-private-l1-1-0!_o_isalpha` at `0x1800566ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056718`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056718`
- `OLEAUT32!__imp_SysFreeString` at `0x18005675a`
- `OLEAUT32!__imp_SysFreeString` at `0x18005675a`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180056694`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180056694`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18005670e`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18005670e`

## pseudocode

```c
__int64 __fastcall RegistryPropertyBag::MetadataCachePathProperty::Read(OLECHAR **this, HKEY a2)
{
  int v4; // ebx
  BSTR *v5; // rdi
  unsigned __int64 v6; // rax
  const WCHAR *v7; // rbx
  DWORD FullPathNameW; // eax
  signed int LastError; // eax
  LPVOID Context; // [rsp+20h] [rbp-248h] BYREF
  WCHAR Buffer[264]; // [rsp+30h] [rbp-238h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_ba44a63574e4389fb68e2aee6092cba5_Traceguids);
  Context = 0;
  if ( InitOnceExecuteOnce(&InitOnce, InitMetadataCachePathProperty, 0, &Context)
    || (v4 = (int)Context, (int)Context >= 0) )
  {
    v4 = RegistryPropertyBag::StringProperty::Read((RegistryPropertyBag::StringProperty *)this, a2);
    if ( v4 >= 0 )
    {
      v5 = this + 2;
      v6 = -1;
      v7 = this[2];
      do
        ++v6;
      while ( v7[v6] );
      if ( v6 < 2 || (*v7 != 92 || v7[1] != 92) && (!(unsigned int)_o_isalpha(*v7) || v7[1] != 58) )
        goto LABEL_22;
      FullPathNameW = GetFullPathNameW(v7, 0x104u, Buffer, 0);
      if ( FullPathNameW )
      {
        if ( FullPathNameW > 0x104 )
          goto LABEL_22;
      }
      else
      {
        LastError = GetLastError();
        v4 = LastError;
        if ( LastError > 0 )
          v4 = (unsigned __int16)LastError | 0x80070000;
        if ( v4 < 0 )
          goto LABEL_23;
      }
      if ( !(unsigned int)_o__wcsnicmp(
                            Buffer,
                            &RegistryPropertyBag::MetadataCachePathProperty::s_szDeviceMetadataCachePath,
                            RegistryPropertyBag::MetadataCachePathProperty::s_cchDeviceMetadataCachePath) )
      {
        SysFreeString(*v5);
        *v5 = 0;
        v4 = ATL::CComBSTR::Append(this + 2, Buffer);
        goto LABEL_23;
      }
LABEL_22:
      v4 = -2147024735;
    }
  }
LABEL_23:
  *((_DWORD *)this + 6) = v4;
  *((_BYTE *)this + 8) = v4 >= 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      37,
      &WPP_ba44a63574e4389fb68e2aee6092cba5_Traceguids,
      (unsigned int)v4);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18005661c  mov     [rsp+arg_10], rbx
0x180056621  mov     [rsp+arg_18], rbp
0x180056626  push    rsi
0x180056627  push    rdi
0x180056628  push    r15
0x18005662a  sub     rsp, 250h
0x180056631  mov     rax, cs:__security_cookie
0x180056638  xor     rax, rsp
0x18005663b  mov     [rsp+268h+var_28], rax
0x180056643  mov     rdi, rdx
0x180056646  mov     rsi, rcx
0x180056649  mov     rcx, cs:WPP_GLOBAL_Control
0x180056650  lea     r15, WPP_GLOBAL_Control
0x180056657  cmp     rcx, r15
0x18005665a  jz      short loc_180056677
0x18005665c  test    byte ptr [rcx+1Ch], 10h
0x180056660  jz      short loc_180056677
0x180056662  mov     rcx, [rcx+10h]
0x180056666  lea     r8, WPP_ba44a63574e4389fb68e2aee6092cba5_Traceguids
0x18005666d  mov     edx, 24h ; '$'
0x180056672  call    WPP_SF_
0x180056677  xor     ebp, ebp
0x180056679  lea     r9, [rsp+268h+Context]; Context
0x18005667e  xor     r8d, r8d; Parameter
0x180056681  mov     [rsp+268h+Context], rbp
0x180056686  lea     rdx, ?InitMetadataCachePathProperty@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18005668d  lea     rcx, InitOnce; InitOnce
0x180056694  call    cs:__imp_InitOnceExecuteOnce
0x18005669a  test    eax, eax
0x18005669c  jnz     short loc_1800566AA
0x18005669e  mov     ebx, dword ptr [rsp+268h+Context]
0x1800566a2  test    ebx, ebx
0x1800566a4  js      loc_180056779
0x1800566aa  mov     rdx, rdi; HKEY
0x1800566ad  mov     rcx, rsi; this
0x1800566b0  call    ?Read@StringProperty@RegistryPropertyBag@@MEAAJPEAUHKEY__@@@Z; RegistryPropertyBag::StringProperty::Read(HKEY__ *)
0x1800566b5  mov     ebx, eax
0x1800566b7  test    eax, eax
0x1800566b9  js      loc_180056779
0x1800566bf  lea     rdi, [rsi+10h]
0x1800566c3  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800566c7  mov     rbx, [rdi]
0x1800566ca  inc     rax
0x1800566cd  cmp     [rbx+rax*2], bp
0x1800566d1  jnz     short loc_1800566CA
0x1800566d3  cmp     rax, 2
0x1800566d7  jb      loc_180056774
0x1800566dd  cmp     word ptr [rbx], 5Ch ; '\'
0x1800566e1  jnz     short loc_1800566EA
0x1800566e3  cmp     word ptr [rbx+2], 5Ch ; '\'
0x1800566e8  jz      short loc_1800566FE
0x1800566ea  movzx   ecx, word ptr [rbx]
0x1800566ed  call    cs:__imp__o_isalpha
0x1800566f3  test    eax, eax
0x1800566f5  jz      short loc_180056774
0x1800566f7  cmp     word ptr [rbx+2], 3Ah ; ':'
0x1800566fc  jnz     short loc_180056774
0x1800566fe  xor     r9d, r9d; lpFilePart
0x180056701  lea     r8, [rsp+268h+Buffer]; lpBuffer
0x180056706  mov     edx, 104h; nBufferLength
0x18005670b  mov     rcx, rbx; lpFileName
0x18005670e  call    cs:__imp_GetFullPathNameW
0x180056714  test    eax, eax
0x180056716  jnz     short loc_180056733
0x180056718  call    cs:__imp_GetLastError
0x18005671e  mov     ebx, eax
0x180056720  test    eax, eax
0x180056722  jle     short loc_18005672D
0x180056724  movzx   ebx, ax
0x180056727  or      ebx, 80070000h
0x18005672d  test    ebx, ebx
0x18005672f  jns     short loc_18005673A
0x180056731  jmp     short loc_180056779
0x180056733  cmp     eax, 104h
0x180056738  ja      short loc_180056774
0x18005673a  movsxd  r8, cs:?s_cchDeviceMetadataCachePath@MetadataCachePathProperty@RegistryPropertyBag@@0HA; int RegistryPropertyBag::MetadataCachePathProperty::s_cchDeviceMetadataCachePath
0x180056741  lea     rdx, ?s_szDeviceMetadataCachePath@MetadataCachePathProperty@RegistryPropertyBag@@0PAGA; ushort near * RegistryPropertyBag::MetadataCachePathProperty::s_szDeviceMetadataCachePath
0x180056748  lea     rcx, [rsp+268h+Buffer]
0x18005674d  call    cs:__imp__o__wcsnicmp
0x180056753  test    eax, eax
0x180056755  jnz     short loc_180056774
0x180056757  mov     rcx, [rdi]; bstrString
0x18005675a  call    cs:__imp_SysFreeString
0x180056760  lea     rdx, [rsp+268h+Buffer]; unsigned __int16 *
0x180056765  mov     [rdi], rbp
0x180056768  mov     rcx, rdi; this
0x18005676b  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x180056770  mov     ebx, eax
0x180056772  jmp     short loc_180056779
0x180056774  mov     ebx, 800700A1h
0x180056779  mov     eax, ebx
0x18005677b  mov     [rsi+18h], ebx
0x18005677e  shr     eax, 1Fh
0x180056781  xor     al, 1
0x180056783  mov     [rsi+8], al
0x180056786  mov     rcx, cs:WPP_GLOBAL_Control
0x18005678d  cmp     rcx, r15
0x180056790  jz      short loc_1800567B0
0x180056792  test    byte ptr [rcx+1Ch], 10h
0x180056796  jz      short loc_1800567B0
0x180056798  mov     rcx, [rcx+10h]
0x18005679c  lea     r8, WPP_ba44a63574e4389fb68e2aee6092cba5_Traceguids
0x1800567a3  mov     edx, 25h ; '%'
0x1800567a8  mov     r9d, ebx
0x1800567ab  call    WPP_SF_d
0x1800567b0  mov     eax, ebx
0x1800567b2  mov     rcx, [rsp+268h+var_28]
0x1800567ba  xor     rcx, rsp; StackCookie
0x1800567bd  call    __security_check_cookie
0x1800567c2  lea     r11, [rsp+268h+var_18]
0x1800567ca  mov     rbx, [r11+30h]
0x1800567ce  mov     rbp, [r11+38h]
0x1800567d2  mov     rsp, r11
0x1800567d5  pop     r15
0x1800567d7  pop     rdi
0x1800567d8  pop     rsi
0x1800567d9  retn
```
