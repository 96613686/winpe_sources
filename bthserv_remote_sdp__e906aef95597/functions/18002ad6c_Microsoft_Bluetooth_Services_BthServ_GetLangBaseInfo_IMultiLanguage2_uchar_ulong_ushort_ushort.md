# Microsoft::Bluetooth::Services::BthServ::GetLangBaseInfo(IMultiLanguage2 *,uchar *,ulong,ushort *,ushort *)

- ea: `0x18002ad6c`
- end: `0x18002b025`
- name: `?GetLangBaseInfo@BthServ@Services@Bluetooth@Microsoft@@YAKPEAUIMultiLanguage2@@PEAEKPEAG2@Z`
- size: `697`
- prototype: `unsigned int __fastcall(Microsoft::Bluetooth::Services::BthServ *this, struct IMultiLanguage2 *, unsigned __int8 *, SHORT *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002aa48`

## callees

- `0x1800017a0`
- `0x18002a5cc`
- `0x18002a6c0`
- `0x18002ad6c`
- `0x1800362f0`
- `0x180036d0c`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x18002ae31`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x18002ae31`
- `OLEAUT32!__imp_SysAllocString` at `0x18002aeb7`
- `OLEAUT32!__imp_SysAllocString` at `0x18002aeb7`
- `OLEAUT32!__imp_SysFreeString` at `0x18002aefe`
- `OLEAUT32!__imp_SysFreeString` at `0x18002aefe`

## pseudocode

```c
unsigned int __fastcall Microsoft::Bluetooth::Services::BthServ::GetLangBaseInfo(
        Microsoft::Bluetooth::Services::BthServ *this,
        struct IMultiLanguage2 *a2,
        unsigned __int8 *a3,
        SHORT *a4,
        unsigned __int16 *a5)
{
  Microsoft::Bluetooth::Services::BthServ *v5; // r13
  ULONG length; // edi
  unsigned __int8 *value; // rsi
  __int16 v9; // r14
  unsigned __int16 uint16; // bx
  BSTR v11; // rax
  int v12; // ebx
  __int16 v13; // r13
  unsigned int result; // eax
  ULONG v15; // edi
  Microsoft::Bluetooth::Services::BthServ *LowPart; // rbx
  SHORT int16; // si
  SHORT v18; // [rsp+30h] [rbp-51h]
  unsigned int v19[2]; // [rsp+38h] [rbp-49h] BYREF
  struct _SDP_ELEMENT_DATA v20; // [rsp+40h] [rbp-41h] BYREF
  int v21; // [rsp+58h] [rbp-29h] BYREF
  _DWORD v22[3]; // [rsp+5Ch] [rbp-25h]
  Microsoft::Bluetooth::Services::BthServ *v23; // [rsp+68h] [rbp-19h]
  Microsoft::Bluetooth::Services::BthServ *v24; // [rsp+70h] [rbp-11h]
  OLECHAR psz[4]; // [rsp+78h] [rbp-9h] BYREF

  v5 = this;
  v23 = this;
  v22[0] = (_DWORD)a3;
  v24 = (Microsoft::Bluetooth::Services::BthServ *)a2;
  memset(&v20, 0, sizeof(v20));
  if ( Microsoft::Bluetooth::Services::BthServ::BluetoothSdpGetAttributeValue(
         (Microsoft::Bluetooth::Services::BthServ *)a2,
         (unsigned __int8 *)(unsigned int)a3,
         6,
         &v20) )
  {
    return 0;
  }
  if ( v20.type != SDP_TYPE_SEQUENCE )
    return 87;
  length = v20.data.string.length;
  value = v20.data.string.value;
  if ( (int)SdpValidateStream(v20.data.int32, v20.data.string.length, 0, 0, 0) < 0
    || (int)SdpVerifyServiceRecord(value) < 0 )
  {
    return 87;
  }
  v21 = 0;
  *(_QWORD *)v19 = 0;
  v9 = GetThreadLocale() & 0x3FF;
  if ( Microsoft::Bluetooth::Services::BthServ::BluetoothSdpGetContainerElementData(
         (Microsoft::Bluetooth::Services::BthServ *)value,
         (unsigned __int8 *)length,
         (Microsoft::Bluetooth::Services::BthServ **)v19,
         &v20) == 259 )
  {
LABEL_15:
    Microsoft::Bluetooth::Services::BthServ::BluetoothSdpGetAttributeValue(v24, (unsigned __int8 *)v22[0], 6, &v20);
    v15 = v20.data.string.length;
    *(_QWORD *)v19 = 0;
    LowPart = (Microsoft::Bluetooth::Services::BthServ *)v20.data.int128.LowPart;
    result = Microsoft::Bluetooth::Services::BthServ::BluetoothSdpGetContainerElementData(
               (Microsoft::Bluetooth::Services::BthServ *)v20.data.int128.LowPart,
               (unsigned __int8 *)v20.data.string.length,
               (Microsoft::Bluetooth::Services::BthServ **)v19,
               &v20);
    if ( result != 259 )
    {
      while ( !result )
      {
        Microsoft::Bluetooth::Services::BthServ::BluetoothSdpGetContainerElementData(
          LowPart,
          (unsigned __int8 *)v15,
          (Microsoft::Bluetooth::Services::BthServ **)v19,
          &v20);
        int16 = v20.data.int16;
        Microsoft::Bluetooth::Services::BthServ::BluetoothSdpGetContainerElementData(
          LowPart,
          (unsigned __int8 *)v15,
          (Microsoft::Bluetooth::Services::BthServ **)v19,
          &v20);
        if ( v20.data.int16 == 256 )
        {
          *a4 = int16;
          *a5 = 256;
          return 0;
        }
        result = Microsoft::Bluetooth::Services::BthServ::BluetoothSdpGetContainerElementData(
                   LowPart,
                   (unsigned __int8 *)v15,
                   (Microsoft::Bluetooth::Services::BthServ **)v19,
                   &v20);
        if ( result == 259 )
          return 0;
      }
      return result;
    }
    return 0;
  }
  while ( 1 )
  {
    uint16 = v20.data.uint16;
    Microsoft::Bluetooth::Services::BthServ::BluetoothSdpGetContainerElementData(
      (Microsoft::Bluetooth::Services::BthServ *)value,
      (unsigned __int8 *)length,
      (Microsoft::Bluetooth::Services::BthServ **)v19,
      &v20);
    v18 = v20.data.int16;
    Microsoft::Bluetooth::Services::BthServ::BluetoothSdpGetContainerElementData(
      (Microsoft::Bluetooth::Services::BthServ *)value,
      (unsigned __int8 *)length,
      (Microsoft::Bluetooth::Services::BthServ **)v19,
      &v20);
    psz[0] = HIBYTE(uint16);
    psz[1] = (unsigned __int8)uint16;
    psz[2] = 0;
    v11 = SysAllocString(psz);
    *(_QWORD *)&v22[1] = v11;
    if ( !v11 )
      return 1450;
    v12 = (*(__int64 (__fastcall **)(Microsoft::Bluetooth::Services::BthServ *, int *, BSTR))(*(_QWORD *)v5 + 112LL))(
            v5,
            &v21,
            v11);
    v13 = v21 & 0x3FF;
    SysFreeString(*(BSTR *)&v22[1]);
    if ( v12 >= 0 && v13 == v9 )
    {
      *a4 = v18;
      *a5 = v20.data.uint16;
      return 0;
    }
    if ( Microsoft::Bluetooth::Services::BthServ::BluetoothSdpGetContainerElementData(
           (Microsoft::Bluetooth::Services::BthServ *)value,
           (unsigned __int8 *)length,
           (Microsoft::Bluetooth::Services::BthServ **)v19,
           &v20) == 259 )
      goto LABEL_15;
    v5 = v23;
  }
}

```

## disassembly

```asm
0x18002ad6c  push    rbp
0x18002ad6e  push    rbx
0x18002ad6f  push    rsi
0x18002ad70  push    rdi
0x18002ad71  push    r12
0x18002ad73  push    r13
0x18002ad75  push    r14
0x18002ad77  push    r15
0x18002ad79  lea     rbp, [rsp-17h]
0x18002ad7e  sub     rsp, 98h
0x18002ad85  mov     rax, cs:__security_cookie
0x18002ad8c  xor     rax, rsp
0x18002ad8f  mov     [rbp+4Fh+var_50], rax
0x18002ad93  mov     r12, [rbp+4Fh+arg_20]
0x18002ad97  mov     r13, rcx
0x18002ad9a  mov     [rbp+4Fh+var_68], rcx
0x18002ad9e  mov     r10d, r8d
0x18002ada1  xor     ecx, ecx
0x18002ada3  mov     dword ptr [rbp+4Fh+var_74], r8d
0x18002ada7  mov     rax, rdx
0x18002adaa  mov     [rbp+4Fh+var_60], rdx
0x18002adae  mov     r15, r9
0x18002adb1  mov     [rbp+4Fh+var_80], rcx
0x18002adb5  xorps   xmm0, xmm0
0x18002adb8  lea     r9, [rbp+4Fh+var_90]; unsigned __int16
0x18002adbc  lea     r14d, [rcx+6]
0x18002adc0  mov     edx, r10d; unsigned __int8 *
0x18002adc3  mov     r8d, r14d; unsigned int
0x18002adc6  mov     rcx, rax; this
0x18002adc9  movups  xmmword ptr [rbp+4Fh+var_90], xmm0
0x18002adcd  call    ?BluetoothSdpGetAttributeValue@BthServ@Services@Bluetooth@Microsoft@@YAKPEAEKGPEAU_SDP_ELEMENT_DATA@@@Z; Microsoft::Bluetooth::Services::BthServ::BluetoothSdpGetAttributeValue(uchar *,ulong,ushort,_SDP_ELEMENT_DATA *)
0x18002add2  xor     ebx, ebx
0x18002add4  test    eax, eax
0x18002add6  jnz     loc_18002AF4B
0x18002addc  cmp     dword ptr [rbp+4Fh+var_90], r14d
0x18002ade0  jnz     loc_18002B01B
0x18002ade6  mov     rdi, [rbp+4Fh+var_80]
0x18002adea  xor     r9d, r9d
0x18002aded  mov     rsi, [rbp+4Fh+var_90+8]
0x18002adf1  mov     edx, edi
0x18002adf3  mov     rcx, rsi
0x18002adf6  mov     [rsp+0D0h+var_B0], rbx; struct _SDP_ELEMENT_DATA *
0x18002adfb  xor     r8d, r8d
0x18002adfe  call    SdpValidateStream
0x18002ae03  test    eax, eax
0x18002ae05  js      loc_18002B01B
0x18002ae0b  lea     r9, [rbp+4Fh+var_A0]
0x18002ae0f  mov     [rbp+4Fh+var_A0], r14w
0x18002ae14  lea     r8d, [r14+2]
0x18002ae18  mov     edx, edi
0x18002ae1a  mov     rcx, rsi; unsigned __int8 *
0x18002ae1d  call    SdpVerifyServiceRecord
0x18002ae22  test    eax, eax
0x18002ae24  js      loc_18002B01B
0x18002ae2a  mov     [rbp+4Fh+var_78], ebx
0x18002ae2d  mov     qword ptr [rbp+4Fh+var_98], rbx
0x18002ae31  call    cs:__imp_GetThreadLocale
0x18002ae38  nop     dword ptr [rax+rax+00h]
0x18002ae3d  lea     r9, [rbp+4Fh+var_90]; void **
0x18002ae41  mov     edx, edi; unsigned __int8 *
0x18002ae43  mov     r14d, eax
0x18002ae46  lea     r8, [rbp+4Fh+var_98]; unsigned int
0x18002ae4a  mov     eax, 3FFh
0x18002ae4f  mov     rcx, rsi; this
0x18002ae52  and     r14w, ax
0x18002ae56  call    ?BluetoothSdpGetContainerElementData@BthServ@Services@Bluetooth@Microsoft@@YAKPEAEKPEAPEAXPEAU_SDP_ELEMENT_DATA@@@Z; Microsoft::Bluetooth::Services::BthServ::BluetoothSdpGetContainerElementData(uchar *,ulong,void * *,_SDP_ELEMENT_DATA *)
0x18002ae5b  cmp     eax, 103h
0x18002ae60  jz      loc_18002AF79
0x18002ae66  movzx   ebx, word ptr [rbp+4Fh+var_90+8]
0x18002ae6a  lea     r9, [rbp+4Fh+var_90]; void **
0x18002ae6e  lea     r8, [rbp+4Fh+var_98]; unsigned int
0x18002ae72  mov     edx, edi; unsigned __int8 *
0x18002ae74  mov     rcx, rsi; this
0x18002ae77  call    ?BluetoothSdpGetContainerElementData@BthServ@Services@Bluetooth@Microsoft@@YAKPEAEKPEAPEAXPEAU_SDP_ELEMENT_DATA@@@Z; Microsoft::Bluetooth::Services::BthServ::BluetoothSdpGetContainerElementData(uchar *,ulong,void * *,_SDP_ELEMENT_DATA *)
0x18002ae7c  movzx   eax, word ptr [rbp+4Fh+var_90+8]
0x18002ae80  lea     r9, [rbp+4Fh+var_90]; void **
0x18002ae84  lea     r8, [rbp+4Fh+var_98]; unsigned int
0x18002ae88  mov     [rbp+4Fh+var_A0], ax
0x18002ae8c  mov     edx, edi; unsigned __int8 *
0x18002ae8e  mov     rcx, rsi; this
0x18002ae91  call    ?BluetoothSdpGetContainerElementData@BthServ@Services@Bluetooth@Microsoft@@YAKPEAEKPEAPEAXPEAU_SDP_ELEMENT_DATA@@@Z; Microsoft::Bluetooth::Services::BthServ::BluetoothSdpGetContainerElementData(uchar *,ulong,void * *,_SDP_ELEMENT_DATA *)
0x18002ae96  movzx   eax, bx
0x18002ae99  lea     rcx, [rbp+4Fh+psz]; psz
0x18002ae9d  shr     ax, 8
0x18002aea1  mov     [rbp+4Fh+psz], ax
0x18002aea5  mov     eax, 0FFh
0x18002aeaa  and     bx, ax
0x18002aead  mov     [rbp+4Fh+var_56], bx
0x18002aeb1  xor     ebx, ebx
0x18002aeb3  mov     [rbp+4Fh+var_54], bx
0x18002aeb7  call    cs:__imp_SysAllocString
0x18002aebe  nop     dword ptr [rax+rax+00h]
0x18002aec3  mov     qword ptr [rbp+4Fh+var_74+4], rax
0x18002aec7  mov     rdx, rax
0x18002aeca  test    rax, rax
0x18002aecd  jz      loc_18002AF6E
0x18002aed3  mov     rcx, [r13+0]
0x18002aed7  mov     r8, rdx
0x18002aeda  lea     rdx, [rbp+4Fh+var_78]
0x18002aede  mov     rax, [rcx+70h]
0x18002aee2  mov     rcx, r13
0x18002aee5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002aeea  movzx   r13d, word ptr [rbp+4Fh+var_78]
0x18002aeef  mov     ebx, eax
0x18002aef1  mov     rcx, qword ptr [rbp+4Fh+var_74+4]; bstrString
0x18002aef5  mov     eax, 3FFh
0x18002aefa  and     r13w, ax
0x18002aefe  call    cs:__imp_SysFreeString
0x18002af05  nop     dword ptr [rax+rax+00h]
0x18002af0a  test    ebx, ebx
0x18002af0c  js      short loc_18002AF14
0x18002af0e  cmp     r13w, r14w
0x18002af12  jz      short loc_18002AF3A
0x18002af14  lea     r9, [rbp+4Fh+var_90]; void **
0x18002af18  mov     edx, edi; unsigned __int8 *
0x18002af1a  lea     r8, [rbp+4Fh+var_98]; unsigned int
0x18002af1e  mov     rcx, rsi; this
0x18002af21  call    ?BluetoothSdpGetContainerElementData@BthServ@Services@Bluetooth@Microsoft@@YAKPEAEKPEAPEAXPEAU_SDP_ELEMENT_DATA@@@Z; Microsoft::Bluetooth::Services::BthServ::BluetoothSdpGetContainerElementData(uchar *,ulong,void * *,_SDP_ELEMENT_DATA *)
0x18002af26  mov     r13d, 103h
0x18002af2c  cmp     eax, r13d
0x18002af2f  jz      short loc_18002AF75
0x18002af31  mov     r13, [rbp+4Fh+var_68]
0x18002af35  jmp     loc_18002AE66
0x18002af3a  movzx   eax, [rbp+4Fh+var_A0]
0x18002af3e  mov     [r15], ax
0x18002af42  movzx   eax, word ptr [rbp+4Fh+var_90+8]
0x18002af46  mov     [r12], ax
0x18002af4b  xor     eax, eax
0x18002af4d  mov     rcx, [rbp+4Fh+var_50]
0x18002af51  xor     rcx, rsp; StackCookie
0x18002af54  call    __security_check_cookie
0x18002af59  add     rsp, 98h
0x18002af60  pop     r15
0x18002af62  pop     r14
0x18002af64  pop     r13
0x18002af66  pop     r12
0x18002af68  pop     rdi
0x18002af69  pop     rsi
0x18002af6a  pop     rbx
0x18002af6b  pop     rbp
0x18002af6c  retn
0x18002af6e  mov     eax, 5AAh
0x18002af73  jmp     short loc_18002AF4D
0x18002af75  xor     ebx, ebx
0x18002af77  jmp     short loc_18002AF7F
0x18002af79  mov     r13d, 103h
0x18002af7f  mov     edx, dword ptr [rbp+4Fh+var_74]; unsigned __int8 *
0x18002af82  lea     r9, [rbp+4Fh+var_90]; unsigned __int16
0x18002af86  mov     rcx, [rbp+4Fh+var_60]; this
0x18002af8a  mov     r8d, 6; unsigned int
0x18002af90  call    ?BluetoothSdpGetAttributeValue@BthServ@Services@Bluetooth@Microsoft@@YAKPEAEKGPEAU_SDP_ELEMENT_DATA@@@Z; Microsoft::Bluetooth::Services::BthServ::BluetoothSdpGetAttributeValue(uchar *,ulong,ushort,_SDP_ELEMENT_DATA *)
0x18002af95  mov     rdi, [rbp+4Fh+var_80]
0x18002af99  lea     r9, [rbp+4Fh+var_90]; void **
0x18002af9d  mov     qword ptr [rbp+4Fh+var_98], rbx
0x18002afa1  lea     r8, [rbp+4Fh+var_98]; unsigned int
0x18002afa5  mov     rbx, [rbp+4Fh+var_90+8]
0x18002afa9  mov     edx, edi; unsigned __int8 *
0x18002afab  mov     rcx, rbx; this
0x18002afae  call    ?BluetoothSdpGetContainerElementData@BthServ@Services@Bluetooth@Microsoft@@YAKPEAEKPEAPEAXPEAU_SDP_ELEMENT_DATA@@@Z; Microsoft::Bluetooth::Services::BthServ::BluetoothSdpGetContainerElementData(uchar *,ulong,void * *,_SDP_ELEMENT_DATA *)
0x18002afb3  cmp     eax, r13d
0x18002afb6  jz      short loc_18002AF4B
0x18002afb8  mov     r14d, 100h
0x18002afbe  test    eax, eax
0x18002afc0  jnz     short loc_18002AF4D
0x18002afc2  lea     r9, [rbp+4Fh+var_90]; void **
0x18002afc6  mov     edx, edi; unsigned __int8 *
0x18002afc8  lea     r8, [rbp+4Fh+var_98]; unsigned int
0x18002afcc  mov     rcx, rbx; this
0x18002afcf  call    ?BluetoothSdpGetContainerElementData@BthServ@Services@Bluetooth@Microsoft@@YAKPEAEKPEAPEAXPEAU_SDP_ELEMENT_DATA@@@Z; Microsoft::Bluetooth::Services::BthServ::BluetoothSdpGetContainerElementData(uchar *,ulong,void * *,_SDP_ELEMENT_DATA *)
0x18002afd4  movzx   esi, word ptr [rbp+4Fh+var_90+8]
0x18002afd8  lea     r9, [rbp+4Fh+var_90]; void **
0x18002afdc  lea     r8, [rbp+4Fh+var_98]; unsigned int
0x18002afe0  mov     edx, edi; unsigned __int8 *
0x18002afe2  mov     rcx, rbx; this
0x18002afe5  call    ?BluetoothSdpGetContainerElementData@BthServ@Services@Bluetooth@Microsoft@@YAKPEAEKPEAPEAXPEAU_SDP_ELEMENT_DATA@@@Z; Microsoft::Bluetooth::Services::BthServ::BluetoothSdpGetContainerElementData(uchar *,ulong,void * *,_SDP_ELEMENT_DATA *)
0x18002afea  cmp     r14w, word ptr [rbp+4Fh+var_90+8]
0x18002afef  jz      short loc_18002B00D
0x18002aff1  lea     r9, [rbp+4Fh+var_90]; void **
0x18002aff5  mov     edx, edi; unsigned __int8 *
0x18002aff7  lea     r8, [rbp+4Fh+var_98]; unsigned int
0x18002affb  mov     rcx, rbx; this
0x18002affe  call    ?BluetoothSdpGetContainerElementData@BthServ@Services@Bluetooth@Microsoft@@YAKPEAEKPEAPEAXPEAU_SDP_ELEMENT_DATA@@@Z; Microsoft::Bluetooth::Services::BthServ::BluetoothSdpGetContainerElementData(uchar *,ulong,void * *,_SDP_ELEMENT_DATA *)
0x18002b003  cmp     eax, r13d
0x18002b006  jnz     short loc_18002AFBE
0x18002b008  jmp     loc_18002AF4B
0x18002b00d  mov     [r15], si
0x18002b011  mov     [r12], r14w
0x18002b016  jmp     loc_18002AF4B
0x18002b01b  mov     eax, 57h ; 'W'
0x18002b020  jmp     loc_18002AF4D
```
