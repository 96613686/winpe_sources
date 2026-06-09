# Microsoft::Bluetooth::Services::BthServ::BluetoothSdpGetString(uchar *,ulong,_SDP_STRING_TYPE_DATA *,ushort,ushort *,ulong *)

- ea: `0x18002aa48`
- end: `0x18002ad66`
- name: `?BluetoothSdpGetString@BthServ@Services@Bluetooth@Microsoft@@YAKPEAEKPEAU_SDP_STRING_TYPE_DATA@@GPEAGPEAK@Z`
- size: `798`
- prototype: `__int64 __fastcall(struct IMultiLanguage2 *this, unsigned __int8 *, __int64, struct _SDP_STRING_TYPE_DATA *, __int64, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180026b94`
- `0x180027848`

## callees

- `0x1800017a0`
- `0x18000270c`
- `0x18002a5cc`
- `0x18002aa48`
- `0x18002ad6c`
- `0x180039010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18002ac1a`
- `OLEAUT32!__imp_SysAllocString` at `0x18002ac1a`
- `OLEAUT32!__imp_SysFreeString` at `0x18002ad28`
- `OLEAUT32!__imp_SysFreeString` at `0x18002ad28`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002ab11`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002ab11`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18002aac6`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18002aac6`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18002abfd`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18002abfd`

## pseudocode

```c
__int64 __fastcall Microsoft::Bluetooth::Services::BthServ::BluetoothSdpGetString(
        struct IMultiLanguage2 *this,
        unsigned __int8 *a2,
        __int64 a3,
        struct _SDP_STRING_TYPE_DATA *a4,
        __int64 a5,
        unsigned __int16 *a6)
{
  __int16 v6; // r13
  unsigned int v7; // esi
  HRESULT v9; // r14d
  int Instance; // ebx
  SDP_SPECIFICTYPE length; // r15d
  int v13; // ecx
  int v14; // edx
  unsigned int v15; // r8d
  unsigned __int16 v16; // r9
  const OLECHAR *v17; // rcx
  BSTR v18; // rax
  OLECHAR *v19; // rsi
  ULONGLONG LowPart; // r13
  char v21; // r15
  SDP_TYPE type; // eax
  bool v23; // cf
  unsigned __int16 *v24; // [rsp+28h] [rbp-B1h]
  _SDP_ELEMENT_DATA ppv; // [rsp+40h] [rbp-99h] BYREF
  struct _SDP_ELEMENT_DATA v26; // [rsp+58h] [rbp-81h] BYREF
  _BYTE v27[4]; // [rsp+70h] [rbp-69h] BYREF
  unsigned int v28; // [rsp+74h] [rbp-65h]

  v6 = (__int16)a4;
  v7 = (unsigned int)a2;
  memset(&v26, 0, sizeof(v26));
  if ( !this || !(_DWORD)a2 || !a6 )
    return 87;
  memset_0(v27, 0, 0x6Cu);
  ppv.data.int128.LowPart = 0;
  v9 = CoInitializeEx(0, 2u);
  if ( (int)(v9 + 0x80000000) >= 0 && v9 != -2147417850 )
    return (unsigned int)v9;
  Instance = CoCreateInstance(
               &CLSID_CMultiLanguage,
               0,
               1u,
               &GUID_dccfc164_2b38_11d2_b7ec_00c04f8f5d9a,
               (LPVOID *)&ppv.data);
  if ( Instance >= 0 )
  {
    LOWORD(ppv.specificType) = 106;
    LOWORD(ppv.type) = 256;
    Instance = Microsoft::Bluetooth::Services::BthServ::GetLangBaseInfo(
                 (Microsoft::Bluetooth::Services::BthServ *)ppv.data.int128.LowPart,
                 this,
                 (unsigned __int8 *)v7,
                 (unsigned int)&ppv.specificType,
                 (unsigned __int16 *)&ppv,
                 v24);
    if ( !Instance )
    {
      Instance = Microsoft::Bluetooth::Services::BthServ::BluetoothSdpGetAttributeValue(
                   (Microsoft::Bluetooth::Services::BthServ *)this,
                   (unsigned __int8 *)v7,
                   v6 + LOWORD(ppv.type),
                   &v26);
      if ( !Instance )
      {
        if ( v26.type != SDP_TYPE_STRING )
        {
          Instance = 87;
          goto LABEL_21;
        }
        length = v26.data.string.length;
        if ( !v26.data.string.length )
        {
          *(_DWORD *)a6 = 0;
          Instance = 0;
          goto LABEL_21;
        }
        v13 = 0;
        v14 = 59;
        while ( 1 )
        {
          v15 = (unsigned int)(v14 + v13) >> 1;
          v16 = qword_18003B590[2 * v15];
          if ( LOWORD(ppv.specificType) == v16 )
            break;
          if ( LOWORD(ppv.specificType) <= v16 )
            v14 = v15 - 1;
          else
            v13 = v15 + 1;
          if ( v13 > v14 )
            goto LABEL_20;
        }
        v17 = (const OLECHAR *)qword_18003B590[2 * ((unsigned int)(v14 + v13) >> 1) + 1];
        if ( !v17 )
        {
LABEL_20:
          Instance = 13;
          goto LABEL_21;
        }
        v18 = SysAllocString(v17);
        v19 = v18;
        if ( !v18 )
        {
          Instance = 1450;
          goto LABEL_21;
        }
        if ( (*(int (__fastcall **)(ULONGLONG, BSTR, _BYTE *))(*(_QWORD *)ppv.data.int128.LowPart + 56LL))(
               ppv.data.int128.LowPart,
               v18,
               v27) >= 0 )
        {
          ppv.data.string.length = 0;
          ppv.type = SDP_TYPE_NIL;
          LowPart = v26.data.int128.LowPart;
          ppv.specificType = length;
          v21 = *(_BYTE *)((unsigned int)(length - 1) + v26.data.int128.LowPart);
          if ( !(*(unsigned int (__fastcall **)(ULONGLONG, ULONG *, _QWORD, ULONGLONG, SDP_SPECIFICTYPE *, _QWORD, _SDP_ELEMENT_DATA *))(*(_QWORD *)ppv.data.int128.LowPart + 80LL))(
                  ppv.data.int128.LowPart,
                  &ppv.data.string.length,
                  v28,
                  v26.data.int128.LowPart,
                  &ppv.specificType,
                  0,
                  &ppv) )
          {
            type = ppv.type;
            if ( v21 )
              type = ++ppv.type;
            if ( a5 )
            {
              v23 = *(_DWORD *)a6 < (unsigned int)type;
              *(_DWORD *)a6 = type;
              if ( !v23 )
              {
                if ( (*(unsigned int (__fastcall **)(ULONGLONG, ULONG *, _QWORD, ULONGLONG, SDP_SPECIFICTYPE *, __int64, _SDP_ELEMENT_DATA *))(*(_QWORD *)ppv.data.int128.LowPart + 80LL))(
                       ppv.data.int128.LowPart,
                       &ppv.data.string.length,
                       v28,
                       LowPart,
                       &ppv.specificType,
                       a5,
                       &ppv) )
                {
                  Instance = 13;
                }
                else
                {
                  if ( v21 )
                    *(_WORD *)(a5 + 2LL * (unsigned int)ppv.type) = 0;
                  Instance = 0;
                }
                goto LABEL_42;
              }
            }
            else
            {
              *(_DWORD *)a6 = type;
            }
            Instance = 234;
          }
        }
LABEL_42:
        SysFreeString(v19);
      }
    }
  }
LABEL_21:
  if ( ppv.data.int128.LowPart )
  {
    (*(void (__fastcall **)(ULONGLONG))(*(_QWORD *)ppv.data.int128.LowPart + 16LL))(ppv.data.int128.LowPart);
    ppv.data.int128.LowPart = 0;
  }
  if ( v9 >= 0 )
    CoUninitialize();
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18002aa48  mov     [rsp-8+arg_10], rbx
0x18002aa4d  push    rbp
0x18002aa4e  push    rsi
0x18002aa4f  push    rdi
0x18002aa50  push    r12
0x18002aa52  push    r13
0x18002aa54  push    r14
0x18002aa56  push    r15
0x18002aa58  lea     rbp, [rsp-17h]
0x18002aa5d  sub     rsp, 0F0h
0x18002aa64  mov     rax, cs:__security_cookie
0x18002aa6b  xor     rax, rsp
0x18002aa6e  mov     [rbp+47h+var_40], rax
0x18002aa72  mov     r12, [rbp+47h+arg_20]
0x18002aa76  xor     eax, eax
0x18002aa78  mov     rdi, [rbp+47h+arg_28]
0x18002aa7c  xor     ebx, ebx
0x18002aa7e  mov     [rbp+47h+var_B8], rax
0x18002aa82  xorps   xmm0, xmm0
0x18002aa85  movzx   r13d, r9w
0x18002aa89  mov     esi, edx
0x18002aa8b  mov     r15, rcx
0x18002aa8e  movups  xmmword ptr [rsp+120h+var_C8], xmm0
0x18002aa93  test    rcx, rcx
0x18002aa96  jz      loc_18002AD39
0x18002aa9c  test    edx, edx
0x18002aa9e  jz      loc_18002AD39
0x18002aaa4  test    rdi, rdi
0x18002aaa7  jz      loc_18002AD39
0x18002aaad  xor     edx, edx; Val
0x18002aaaf  lea     r8d, [rax+6Ch]; Size
0x18002aab3  lea     rcx, [rbp+47h+var_B0]; void *
0x18002aab7  call    memset_0
0x18002aabc  lea     edx, [rbx+2]; dwCoInit
0x18002aabf  mov     qword ptr [rsp+120h+var_E0.data], rbx
0x18002aac4  xor     ecx, ecx; pvReserved
0x18002aac6  call    cs:__imp_CoInitializeEx
0x18002aacd  nop     dword ptr [rax+rax+00h]
0x18002aad2  mov     r14d, eax
0x18002aad5  mov     eax, 80000000h
0x18002aada  lea     ecx, [r14+rax]
0x18002aade  test    eax, ecx
0x18002aae0  jnz     short loc_18002AAF3
0x18002aae2  cmp     r14d, 80010106h
0x18002aae9  jz      short loc_18002AAF3
0x18002aaeb  mov     eax, r14d
0x18002aaee  jmp     loc_18002AD3E
0x18002aaf3  xor     edx, edx; pUnkOuter
0x18002aaf5  lea     rax, [rsp+120h+var_E0.data]
0x18002aafa  lea     r9, _GUID_dccfc164_2b38_11d2_b7ec_00c04f8f5d9a; riid
0x18002ab01  mov     [rsp+120h+ppv], rax; ppv
0x18002ab06  lea     rcx, CLSID_CMultiLanguage; rclsid
0x18002ab0d  lea     r8d, [rdx+1]; dwClsContext
0x18002ab11  call    cs:__imp_CoCreateInstance
0x18002ab18  nop     dword ptr [rax+rax+00h]
0x18002ab1d  mov     ebx, eax
0x18002ab1f  test    eax, eax
0x18002ab21  js      loc_18002ABDB
0x18002ab27  mov     rcx, qword ptr [rsp+120h+var_E0.data]; this
0x18002ab2c  lea     r9, [rsp+120h+var_E0.specificType]; unsigned int
0x18002ab31  mov     eax, 6Ah ; 'j'
0x18002ab36  mov     r8d, esi; unsigned __int8 *
0x18002ab39  mov     word ptr [rsp+120h+var_E0.specificType], ax
0x18002ab3e  mov     rdx, r15; struct IMultiLanguage2 *
0x18002ab41  mov     eax, 100h
0x18002ab46  mov     word ptr [rsp+120h+var_E0.type], ax
0x18002ab4b  lea     rax, [rsp+120h+var_E0]
0x18002ab50  mov     [rsp+120h+ppv], rax; struct _SDP_ELEMENT_DATA *
0x18002ab55  call    ?GetLangBaseInfo@BthServ@Services@Bluetooth@Microsoft@@YAKPEAUIMultiLanguage2@@PEAEKPEAG2@Z; Microsoft::Bluetooth::Services::BthServ::GetLangBaseInfo(IMultiLanguage2 *,uchar *,ulong,ushort *,ushort *)
0x18002ab5a  mov     ebx, eax
0x18002ab5c  test    eax, eax
0x18002ab5e  jnz     short loc_18002ABDB
0x18002ab60  movzx   r8d, word ptr [rsp+120h+var_E0.type]
0x18002ab66  lea     r9, [rsp+120h+var_C8]; unsigned __int16
0x18002ab6b  add     r8w, r13w; unsigned int
0x18002ab6f  mov     edx, esi; unsigned __int8 *
0x18002ab71  mov     rcx, r15; this
0x18002ab74  call    ?BluetoothSdpGetAttributeValue@BthServ@Services@Bluetooth@Microsoft@@YAKPEAEKGPEAU_SDP_ELEMENT_DATA@@@Z; Microsoft::Bluetooth::Services::BthServ::BluetoothSdpGetAttributeValue(uchar *,ulong,ushort,_SDP_ELEMENT_DATA *)
0x18002ab79  xor     r13d, r13d
0x18002ab7c  mov     ebx, eax
0x18002ab7e  test    eax, eax
0x18002ab80  jnz     short loc_18002ABDB
0x18002ab82  cmp     dword ptr [rsp+120h+var_C8], 4
0x18002ab87  jz      short loc_18002AB8E
0x18002ab89  lea     ebx, [rax+57h]
0x18002ab8c  jmp     short loc_18002ABDB
0x18002ab8e  mov     r15, [rbp+47h+var_B8]
0x18002ab92  test    r15d, r15d
0x18002ab95  jnz     short loc_18002AB9F
0x18002ab97  mov     [rdi], r13d
0x18002ab9a  mov     ebx, r13d
0x18002ab9d  jmp     short loc_18002ABDB
0x18002ab9f  mov     ecx, r13d
0x18002aba2  lea     r10, qword_18003B590
0x18002aba9  mov     edx, 3Bh ; ';'
0x18002abae  lea     eax, [rdx+rcx]
0x18002abb1  shr     eax, 1
0x18002abb3  mov     r8d, eax
0x18002abb6  add     rax, rax
0x18002abb9  movzx   r9d, word ptr [r10+rax*8]
0x18002abbe  cmp     word ptr [rsp+120h+var_E0.specificType], r9w
0x18002abc4  jz      short loc_18002AC10
0x18002abc6  jbe     short loc_18002ABCE
0x18002abc8  lea     ecx, [r8+1]
0x18002abcc  jmp     short loc_18002ABD2
0x18002abce  lea     edx, [r8-1]
0x18002abd2  cmp     ecx, edx
0x18002abd4  jle     short loc_18002ABAE
0x18002abd6  mov     ebx, 0Dh
0x18002abdb  mov     rcx, qword ptr [rsp+120h+var_E0.data]
0x18002abe0  xor     edi, edi
0x18002abe2  test    rcx, rcx
0x18002abe5  jz      short loc_18002ABF8
0x18002abe7  mov     rax, [rcx]
0x18002abea  mov     rax, [rax+10h]
0x18002abee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002abf3  mov     qword ptr [rsp+120h+var_E0.data], rdi
0x18002abf8  test    r14d, r14d
0x18002abfb  js      short loc_18002AC09
0x18002abfd  call    cs:__imp_CoUninitialize
0x18002ac04  nop     dword ptr [rax+rax+00h]
0x18002ac09  mov     eax, ebx
0x18002ac0b  jmp     loc_18002AD3E
0x18002ac10  mov     rcx, [r10+rax*8+8]; psz
0x18002ac15  test    rcx, rcx
0x18002ac18  jz      short loc_18002ABD6
0x18002ac1a  call    cs:__imp_SysAllocString
0x18002ac21  nop     dword ptr [rax+rax+00h]
0x18002ac26  mov     rsi, rax
0x18002ac29  test    rax, rax
0x18002ac2c  jnz     short loc_18002AC35
0x18002ac2e  mov     ebx, 5AAh
0x18002ac33  jmp     short loc_18002ABDB
0x18002ac35  mov     rcx, qword ptr [rsp+120h+var_E0.data]
0x18002ac3a  lea     r8, [rbp+47h+var_B0]
0x18002ac3e  mov     rdx, rsi
0x18002ac41  mov     rax, [rcx]
0x18002ac44  mov     rax, [rax+38h]
0x18002ac48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ac4d  test    eax, eax
0x18002ac4f  js      loc_18002AD25
0x18002ac55  mov     rcx, qword ptr [rsp+120h+var_E0.data]
0x18002ac5a  lea     eax, [r15-1]
0x18002ac5e  mov     r8d, [rbp+47h+var_AC]
0x18002ac62  lea     rdx, [rsp+120h+var_E0]
0x18002ac67  mov     [rsp+120h+var_F0], rdx
0x18002ac6c  lea     rdx, [rsp+120h+var_E0.specificType]
0x18002ac71  and     [rsp+120h+var_F8], 0
0x18002ac77  mov     dword ptr [rsp+120h+var_E0.data+8], r13d
0x18002ac7c  mov     [rsp+120h+var_E0.type], r13d
0x18002ac81  mov     r13, qword ptr [rbp+47h+var_C8+8]
0x18002ac85  mov     [rsp+120h+var_E0.specificType], r15d
0x18002ac8a  mov     r9, r13
0x18002ac8d  mov     [rsp+120h+ppv], rdx
0x18002ac92  lea     rdx, [rsp+120h+var_E0.data+8]
0x18002ac97  mov     r15b, [rax+r13]
0x18002ac9b  mov     rax, [rcx]
0x18002ac9e  mov     rax, [rax+50h]
0x18002aca2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002aca7  test    eax, eax
0x18002aca9  jnz     short loc_18002AD25
0x18002acab  mov     eax, [rsp+120h+var_E0.type]
0x18002acaf  test    r15b, r15b
0x18002acb2  jz      short loc_18002ACBA
0x18002acb4  inc     eax
0x18002acb6  mov     [rsp+120h+var_E0.type], eax
0x18002acba  test    r12, r12
0x18002acbd  jnz     short loc_18002ACC3
0x18002acbf  mov     [rdi], eax
0x18002acc1  jmp     short loc_18002ACC9
0x18002acc3  cmp     [rdi], eax
0x18002acc5  mov     [rdi], eax
0x18002acc7  jnb     short loc_18002ACD0
0x18002acc9  mov     ebx, 0EAh
0x18002acce  jmp     short loc_18002AD25
0x18002acd0  mov     rcx, qword ptr [rsp+120h+var_E0.data]
0x18002acd5  lea     rdx, [rsp+120h+var_E0]
0x18002acda  mov     r8d, [rbp+47h+var_AC]
0x18002acde  mov     r9, r13
0x18002ace1  mov     [rsp+120h+var_F0], rdx
0x18002ace6  lea     rdx, [rsp+120h+var_E0.specificType]
0x18002aceb  mov     [rsp+120h+var_F8], r12
0x18002acf0  mov     rax, [rcx]
0x18002acf3  mov     [rsp+120h+ppv], rdx
0x18002acf8  lea     rdx, [rsp+120h+var_E0.data+8]
0x18002acfd  mov     rax, [rax+50h]
0x18002ad01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ad06  xor     r13d, r13d
0x18002ad09  test    eax, eax
0x18002ad0b  jnz     short loc_18002AD20
0x18002ad0d  test    r15b, r15b
0x18002ad10  jz      short loc_18002AD1B
0x18002ad12  mov     eax, [rsp+120h+var_E0.type]
0x18002ad16  mov     [r12+rax*2], r13w
0x18002ad1b  mov     ebx, r13d
0x18002ad1e  jmp     short loc_18002AD25
0x18002ad20  mov     ebx, 0Dh
0x18002ad25  mov     rcx, rsi; bstrString
0x18002ad28  call    cs:__imp_SysFreeString
0x18002ad2f  nop     dword ptr [rax+rax+00h]
0x18002ad34  jmp     loc_18002ABDB
0x18002ad39  mov     eax, 57h ; 'W'
0x18002ad3e  mov     rcx, [rbp+47h+var_40]
0x18002ad42  xor     rcx, rsp; StackCookie
0x18002ad45  call    __security_check_cookie
0x18002ad4a  mov     rbx, [rsp+120h+arg_10]
0x18002ad52  add     rsp, 0F0h
0x18002ad59  pop     r15
0x18002ad5b  pop     r14
0x18002ad5d  pop     r13
0x18002ad5f  pop     r12
0x18002ad61  pop     rdi
0x18002ad62  pop     rsi
0x18002ad63  pop     rbp
0x18002ad64  retn
```
