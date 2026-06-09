# CMSEnumDiscRecordersObj::Next(ulong,IDiscRecorder * *,ulong *)

- ea: `0x18000ab90`
- end: `0x18000af6c`
- name: `?Next@CMSEnumDiscRecordersObj@@UEAAJKPEAPEAUIDiscRecorder@@PEAK@Z`
- size: `988`
- prototype: `__int64 __fastcall(CMSEnumDiscRecordersObj *__hidden this, unsigned int, struct IDiscRecorder **, unsigned int *)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180004714`
- `0x180004784`
- `0x180007bac`
- `0x180007bd4`
- `0x18000aaa4`
- `0x18000ab90`
- `0x18000b03c`
- `0x18000fb14`
- `0x180019010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18000acef`
- `ole32!CoCreateInstance` at `0x18000acef`
- `OLEAUT32!__imp_VariantInit` at `0x18000ac80`
- `OLEAUT32!__imp_VariantInit` at `0x18000ac80`
- `OLEAUT32!__imp_VariantClear` at `0x18000accc`
- `OLEAUT32!__imp_VariantClear` at `0x18000accc`

## pseudocode

```c
__int64 __fastcall CMSEnumDiscRecordersObj::Next(
        CMSEnumDiscRecordersObj *this,
        unsigned int a2,
        struct IDiscRecorder **a3,
        unsigned int *a4)
{
  int v6; // ebx
  unsigned int v8; // esi
  unsigned int v9; // r13d
  HRESULT Instance; // eax
  __int64 *v11; // rbx
  __int64 v12; // rdx
  int v13; // eax
  __int64 v14; // r9
  CMSDiscRecorderObj *v15; // r13
  int v16; // eax
  __int64 v17; // r9
  __int64 v18; // rcx
  bool v19; // sf
  _QWORD *v20; // rcx
  __int64 v21; // rdx
  __int64 v22; // r9
  __int64 i; // rdi
  struct IDiscRecorder *v24; // rcx
  int v25; // [rsp+30h] [rbp-40h] BYREF
  __int64 *v26; // [rsp+38h] [rbp-38h] BYREF
  struct IDiscRecorder *v27; // [rsp+40h] [rbp-30h] BYREF
  struct IDiscRecorder2 *ppv; // [rsp+48h] [rbp-28h] BYREF
  CMSDiscRecorderObj *v29; // [rsp+50h] [rbp-20h] BYREF
  VARIANTARG pvarg; // [rsp+58h] [rbp-18h] BYREF

  ppv = 0;
  if ( !a2 )
  {
    if ( a3 && a4 )
    {
      *a4 = 0;
      v6 = 0;
      *a3 = 0;
      return (unsigned int)v6;
    }
    return (unsigned int)-2147024809;
  }
  if ( a2 == 1 )
  {
    if ( !a3 )
      return (unsigned int)-2147024809;
  }
  else if ( !a3 || !a4 )
  {
    return (unsigned int)-2147024809;
  }
  if ( a4 )
    *a4 = 0;
  *a3 = 0;
  if ( *((_QWORD *)this + 8) )
  {
    v8 = 0;
    v9 = a2;
    while ( 1 )
    {
      v26 = 0;
      v25 = 0;
      memset(&pvarg, 0, sizeof(pvarg));
      VariantInit(&pvarg);
      v6 = (*(__int64 (__fastcall **)(_QWORD, __int64, VARIANTARG *))(**((_QWORD **)this + 8) + 24LL))(
             *((_QWORD *)this + 8),
             1,
             &pvarg);
      if ( v6 )
      {
        _bstr_t::~_bstr_t((_bstr_t *)&v26);
        v19 = v6 < 0;
        goto LABEL_69;
      }
      if ( !pvarg.vt )
        break;
      _bstr_t::operator=(&v26, pvarg.llVal);
      VariantClear(&pvarg);
      Instance = CoCreateInstance(
                   &GUID_2735412d_7f64_5b0f_8f00_5d77afbe261e,
                   0,
                   v6 + 23,
                   &GUID_27354133_7f64_5b0f_8f00_5d77afbe261e,
                   (LPVOID *)&ppv);
      v6 = Instance;
      if ( Instance < 0 )
      {
        v20 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
        {
          v21 = 11;
          v22 = (unsigned int)Instance;
LABEL_56:
          WPP_SF_d(v20[7], v21, WPP_4c9bcb71eb6031f620f5f2d14b4181db_Traceguids, v22);
        }
LABEL_61:
        _bstr_t::~_bstr_t((_bstr_t *)&v26);
        goto LABEL_70;
      }
      v11 = v26;
      if ( v26 )
        v12 = *v26;
      else
        v12 = 0;
      v13 = ((__int64 (__fastcall *)(struct IDiscRecorder2 *, __int64))ppv->lpVtbl->InitializeDiscRecorder)(ppv, v12);
      if ( v13 >= 0 )
      {
        v27 = 0;
        v29 = 0;
        if ( (int)ATL::CComObject<CMSDiscRecorderObj>::CreateInstance(&v29) < 0 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 13, WPP_4c9bcb71eb6031f620f5f2d14b4181db_Traceguids);
          v6 = -2147024882;
          goto LABEL_61;
        }
        v15 = v29;
        (*(void (__fastcall **)(CMSDiscRecorderObj *))(*(_QWORD *)v29 + 8LL))(v29);
        v16 = CMSDiscRecorderObj::Init2(v15, ppv);
        ppv = 0;
        if ( v16 >= 0 )
        {
          v6 = (**(__int64 (__fastcall ***)(CMSDiscRecorderObj *, GUID *, struct IDiscRecorder **))v15)(
                 v15,
                 &IID_IDiscRecorder,
                 &v27);
          (*(void (__fastcall **)(CMSDiscRecorderObj *))(*(_QWORD *)v15 + 16LL))(v15);
          if ( v6 < 0 )
          {
            v20 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
            {
              v21 = 15;
              v22 = (unsigned int)v6;
              goto LABEL_56;
            }
            goto LABEL_61;
          }
          v6 = ((__int64 (__fastcall *)(struct IDiscRecorder *, int *))v27->lpVtbl->GetRecorderType)(v27, &v25);
          if ( v25 )
          {
            if ( a4 )
              ++*a4;
            v18 = v8++;
            a3[v18] = v27;
          }
          else
          {
            ((void (__fastcall *)(struct IDiscRecorder *))v27->lpVtbl->Release)(v27);
          }
          v27 = 0;
        }
        else
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
          {
            if ( v11 )
              v17 = *v11;
            else
              LODWORD(v17) = 0;
            WPP_SF_SD(
              *((_QWORD *)WPP_GLOBAL_Control + 7),
              14,
              (unsigned int)WPP_4c9bcb71eb6031f620f5f2d14b4181db_Traceguids,
              v17,
              v16);
          }
          (*(void (__fastcall **)(CMSDiscRecorderObj *))(*(_QWORD *)v15 + 16LL))(v15);
          v6 = 0;
        }
        v9 = a2;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
        {
          if ( v11 )
            v14 = *v11;
          else
            LODWORD(v14) = 0;
          WPP_SF_SD(
            *((_QWORD *)WPP_GLOBAL_Control + 7),
            12,
            (unsigned int)WPP_4c9bcb71eb6031f620f5f2d14b4181db_Traceguids,
            v14,
            v13);
        }
        v6 = 0;
      }
      _bstr_t::~_bstr_t((_bstr_t *)&v26);
      if ( v8 >= v9 )
      {
        v19 = v6 < 0;
        if ( !v6 )
          goto LABEL_66;
LABEL_69:
        if ( !v19 )
          return (unsigned int)v6;
LABEL_70:
        for ( i = 0; (unsigned int)i < v8; i = (unsigned int)(i + 1) )
        {
          v24 = a3[i];
          if ( v24 )
          {
            ((void (__fastcall *)(struct IDiscRecorder *))v24->lpVtbl->Release)(v24);
            a3[i] = 0;
          }
        }
        return (unsigned int)v6;
      }
    }
    _bstr_t::~_bstr_t((_bstr_t *)&v26);
LABEL_66:
    if ( v8 >= v9 )
      return (unsigned int)v6;
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 10, WPP_4c9bcb71eb6031f620f5f2d14b4181db_Traceguids);
  }
  return 1;
}

```

## disassembly

```asm
0x18000ab90  mov     rax, rsp
0x18000ab93  mov     [rax+18h], rbx
0x18000ab97  mov     [rax+20h], rsi
0x18000ab9b  mov     [rax+10h], edx
0x18000ab9e  mov     [rax+8], rcx
0x18000aba2  push    rbp
0x18000aba3  push    rdi
0x18000aba4  push    r13
0x18000aba6  push    r14
0x18000aba8  push    r15
0x18000abaa  mov     rbp, rsp
0x18000abad  sub     rsp, 70h
0x18000abb1  mov     eax, edx
0x18000abb3  mov     rdi, r9
0x18000abb6  xor     edx, edx
0x18000abb8  mov     r14, r8
0x18000abbb  mov     [rbp+var_28], rdx
0x18000abbf  test    eax, eax
0x18000abc1  jnz     short loc_18000ABD7
0x18000abc3  test    r8, r8
0x18000abc6  jz      short loc_18000ABE1
0x18000abc8  test    r9, r9
0x18000abcb  jz      short loc_18000ABE1
0x18000abcd  mov     [r9], edx
0x18000abd0  mov     ebx, edx
0x18000abd2  mov     [r8], rdx
0x18000abd5  jmp     short loc_18000ABE6
0x18000abd7  cmp     eax, 1
0x18000abda  jnz     short loc_18000AC01
0x18000abdc  test    r14, r14
0x18000abdf  jnz     short loc_18000AC0B
0x18000abe1  mov     ebx, 80070057h
0x18000abe6  lea     r11, [rsp+70h+var_s0]
0x18000abeb  mov     eax, ebx
0x18000abed  mov     rbx, [r11+40h]
0x18000abf1  mov     rsi, [r11+48h]
0x18000abf5  mov     rsp, r11
0x18000abf8  pop     r15
0x18000abfa  pop     r14
0x18000abfc  pop     r13
0x18000abfe  pop     rdi
0x18000abff  pop     rbp
0x18000ac00  retn
0x18000ac01  test    r14, r14
0x18000ac04  jz      short loc_18000ABE1
0x18000ac06  test    rdi, rdi
0x18000ac09  jz      short loc_18000ABE1
0x18000ac0b  test    rdi, rdi
0x18000ac0e  jz      short loc_18000AC13
0x18000ac10  mov     [r9], edx
0x18000ac13  mov     [r8], rdx
0x18000ac16  cmp     [rcx+40h], rdx
0x18000ac1a  jnz     short loc_18000AC51
0x18000ac1c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ac23  lea     r15, WPP_GLOBAL_Control
0x18000ac2a  cmp     rcx, r15
0x18000ac2d  jz      short loc_18000AC4A
0x18000ac2f  test    byte ptr [rcx+44h], 1
0x18000ac33  jz      short loc_18000AC4A
0x18000ac35  mov     rcx, [rcx+38h]
0x18000ac39  lea     r8, WPP_4c9bcb71eb6031f620f5f2d14b4181db_Traceguids
0x18000ac40  mov     edx, 0Ah
0x18000ac45  call    WPP_SF_
0x18000ac4a  mov     ebx, 1
0x18000ac4f  jmp     short loc_18000ABE6
0x18000ac51  mov     esi, edx
0x18000ac53  mov     ebx, edx
0x18000ac55  test    eax, eax
0x18000ac57  jz      short loc_18000ABE6
0x18000ac59  mov     r13d, [rbp+arg_8]
0x18000ac5d  lea     r15, WPP_GLOBAL_Control
0x18000ac64  jmp     short loc_18000AC68
0x18000ac66  xor     edx, edx
0x18000ac68  xorps   xmm0, xmm0
0x18000ac6b  mov     [rbp+var_38], rdx
0x18000ac6f  xor     eax, eax
0x18000ac71  mov     [rbp+var_40], edx
0x18000ac74  lea     rcx, [rbp+pvarg]; pvarg
0x18000ac78  mov     qword ptr [rbp+pvarg+10h], rax
0x18000ac7c  movups  xmmword ptr [rbp+pvarg], xmm0
0x18000ac80  call    cs:__imp_VariantInit
0x18000ac86  mov     rax, [rbp+arg_0]
0x18000ac8a  lea     r8, [rbp+pvarg]
0x18000ac8e  xor     r9d, r9d
0x18000ac91  mov     rcx, [rax+40h]
0x18000ac95  lea     edx, [r9+1]
0x18000ac99  mov     rax, [rcx]
0x18000ac9c  mov     rax, [rax+18h]
0x18000aca0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aca5  mov     ebx, eax
0x18000aca7  test    eax, eax
0x18000aca9  jnz     loc_18000AF29
0x18000acaf  xor     ecx, ecx
0x18000acb1  cmp     cx, word ptr [rbp+pvarg]
0x18000acb5  lea     rcx, [rbp+var_38]; this
0x18000acb9  jz      loc_18000AF16
0x18000acbf  mov     rdx, qword ptr [rbp+pvarg+8]
0x18000acc3  call    ??4_bstr_t@@QEAAAEAV0@PEBG@Z; _bstr_t::operator=(ushort const *)
0x18000acc8  lea     rcx, [rbp+pvarg]; pvarg
0x18000accc  call    cs:__imp_VariantClear
0x18000acd2  lea     rax, [rbp+var_28]
0x18000acd6  xor     edx, edx; pUnkOuter
0x18000acd8  lea     r9, _GUID_27354133_7f64_5b0f_8f00_5d77afbe261e; riid
0x18000acdf  mov     [rsp+70h+ppv], rax; ppv
0x18000ace4  lea     r8d, [rbx+17h]; dwClsContext
0x18000ace8  lea     rcx, _GUID_2735412d_7f64_5b0f_8f00_5d77afbe261e; rclsid
0x18000acef  call    cs:__imp_CoCreateInstance
0x18000acf5  mov     ebx, eax
0x18000acf7  test    eax, eax
0x18000acf9  js      loc_18000AEFA
0x18000acff  mov     rcx, [rbp+var_28]
0x18000ad03  mov     rbx, [rbp+var_38]
0x18000ad07  mov     rax, [rcx]
0x18000ad0a  test    rbx, rbx
0x18000ad0d  jz      short loc_18000AD14
0x18000ad0f  mov     rdx, [rbx]
0x18000ad12  jmp     short loc_18000AD16
0x18000ad14  xor     edx, edx
0x18000ad16  mov     rax, [rax+68h]
0x18000ad1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad1f  test    eax, eax
0x18000ad21  jns     short loc_18000AD62
0x18000ad23  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ad2a  cmp     rcx, r15
0x18000ad2d  jz      short loc_18000AD5B
0x18000ad2f  test    byte ptr [rcx+44h], 1
0x18000ad33  jz      short loc_18000AD5B
0x18000ad35  test    rbx, rbx
0x18000ad38  jz      short loc_18000AD3F
0x18000ad3a  mov     r9, [rbx]
0x18000ad3d  jmp     short loc_18000AD42
0x18000ad3f  xor     r9d, r9d
0x18000ad42  mov     rcx, [rcx+38h]
0x18000ad46  lea     r8, WPP_4c9bcb71eb6031f620f5f2d14b4181db_Traceguids
0x18000ad4d  mov     edx, 0Ch
0x18000ad52  mov     dword ptr [rsp+70h+ppv], eax
0x18000ad56  call    WPP_SF_SD
0x18000ad5b  xor     ebx, ebx
0x18000ad5d  jmp     loc_18000AE78
0x18000ad62  lea     rcx, [rbp+var_20]
0x18000ad66  mov     [rbp+var_30], 0
0x18000ad6e  mov     [rbp+var_20], 0
0x18000ad76  call    ?CreateInstance@?$CComObject@VCMSDiscRecorderObj@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CMSDiscRecorderObj>::CreateInstance(ATL::CComObject<CMSDiscRecorderObj> * *)
0x18000ad7b  test    eax, eax
0x18000ad7d  js      loc_18000AEC3
0x18000ad83  mov     r13, [rbp+var_20]
0x18000ad87  mov     rcx, r13
0x18000ad8a  mov     rax, [r13+0]
0x18000ad8e  mov     rax, [rax+8]
0x18000ad92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad97  mov     rdx, [rbp+var_28]; struct IDiscRecorder2 *
0x18000ad9b  mov     rcx, r13; this
0x18000ad9e  call    ?Init2@CMSDiscRecorderObj@@QEAAJPEAUIDiscRecorder2@@@Z; CMSDiscRecorderObj::Init2(IDiscRecorder2 *)
0x18000ada3  mov     [rbp+var_28], 0
0x18000adab  test    eax, eax
0x18000adad  jns     short loc_18000ADFB
0x18000adaf  mov     rcx, cs:WPP_GLOBAL_Control
0x18000adb6  cmp     rcx, r15
0x18000adb9  jz      short loc_18000ADE7
0x18000adbb  test    byte ptr [rcx+44h], 1
0x18000adbf  jz      short loc_18000ADE7
0x18000adc1  test    rbx, rbx
0x18000adc4  jz      short loc_18000ADCB
0x18000adc6  mov     r9, [rbx]
0x18000adc9  jmp     short loc_18000ADCE
0x18000adcb  xor     r9d, r9d
0x18000adce  mov     rcx, [rcx+38h]
0x18000add2  lea     r8, WPP_4c9bcb71eb6031f620f5f2d14b4181db_Traceguids
0x18000add9  mov     edx, 0Eh
0x18000adde  mov     dword ptr [rsp+70h+ppv], eax
0x18000ade2  call    WPP_SF_SD
0x18000ade7  mov     rax, [r13+0]
0x18000adeb  mov     rcx, r13
0x18000adee  mov     rax, [rax+10h]
0x18000adf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000adf7  xor     ebx, ebx
0x18000adf9  jmp     short loc_18000AE74
0x18000adfb  mov     rax, [r13+0]
0x18000adff  lea     r8, [rbp+var_30]
0x18000ae03  lea     rdx, IID_IDiscRecorder
0x18000ae0a  mov     rcx, r13
0x18000ae0d  mov     rax, [rax]
0x18000ae10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae15  mov     ebx, eax
0x18000ae17  mov     rcx, r13
0x18000ae1a  mov     rax, [r13+0]
0x18000ae1e  mov     rax, [rax+10h]
0x18000ae22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae27  test    ebx, ebx
0x18000ae29  js      short loc_18000AE97
0x18000ae2b  mov     rcx, [rbp+var_30]
0x18000ae2f  lea     rdx, [rbp+var_40]
0x18000ae33  mov     rax, [rcx]
0x18000ae36  mov     rax, [rax+28h]
0x18000ae3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae3f  cmp     [rbp+var_40], 0
0x18000ae43  mov     ebx, eax
0x18000ae45  jnz     short loc_18000AE59
0x18000ae47  mov     rcx, [rbp+var_30]
0x18000ae4b  mov     rax, [rcx]
0x18000ae4e  mov     rax, [rax+10h]
0x18000ae52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae57  jmp     short loc_18000AE6C
0x18000ae59  test    rdi, rdi
0x18000ae5c  jz      short loc_18000AE60
0x18000ae5e  inc     dword ptr [rdi]
0x18000ae60  mov     rax, [rbp+var_30]
0x18000ae64  mov     ecx, esi
0x18000ae66  inc     esi
0x18000ae68  mov     [r14+rcx*8], rax
0x18000ae6c  mov     [rbp+var_30], 0
0x18000ae74  mov     r13d, [rbp+arg_8]
0x18000ae78  lea     rcx, [rbp+var_38]; this
0x18000ae7c  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18000ae81  cmp     esi, r13d
0x18000ae84  jb      loc_18000AC66
0x18000ae8a  test    ebx, ebx
0x18000ae8c  jnz     loc_18000AF34
0x18000ae92  jmp     loc_18000AF1B
0x18000ae97  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ae9e  cmp     rcx, r15
0x18000aea1  jz      short loc_18000AEEF
0x18000aea3  test    byte ptr [rcx+44h], 1
0x18000aea7  jz      short loc_18000AEEF
0x18000aea9  mov     edx, 0Fh
0x18000aeae  mov     r9d, ebx
0x18000aeb1  mov     rcx, [rcx+38h]
0x18000aeb5  lea     r8, WPP_4c9bcb71eb6031f620f5f2d14b4181db_Traceguids
0x18000aebc  call    WPP_SF_d
0x18000aec1  jmp     short loc_18000AEEF
0x18000aec3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000aeca  cmp     rcx, r15
0x18000aecd  jz      short loc_18000AEEA
0x18000aecf  test    byte ptr [rcx+44h], 1
0x18000aed3  jz      short loc_18000AEEA
0x18000aed5  mov     rcx, [rcx+38h]
0x18000aed9  lea     r8, WPP_4c9bcb71eb6031f620f5f2d14b4181db_Traceguids
0x18000aee0  mov     edx, 0Dh
0x18000aee5  call    WPP_SF_
0x18000aeea  mov     ebx, 8007000Eh
0x18000aeef  lea     rcx, [rbp+var_38]; this
0x18000aef3  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18000aef8  jmp     short loc_18000AF3A
0x18000aefa  mov     rcx, cs:WPP_GLOBAL_Control
0x18000af01  cmp     rcx, r15
0x18000af04  jz      short loc_18000AEEF
0x18000af06  test    byte ptr [rcx+44h], 1
0x18000af0a  jz      short loc_18000AEEF
0x18000af0c  mov     edx, 0Bh
0x18000af11  mov     r9d, eax
0x18000af14  jmp     short loc_18000AEB1
0x18000af16  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18000af1b  cmp     esi, r13d
0x18000af1e  jnb     loc_18000ABE6
0x18000af24  jmp     loc_18000AC4A
0x18000af29  lea     rcx, [rbp+var_38]; this
0x18000af2d  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x18000af32  test    ebx, ebx
0x18000af34  jns     loc_18000ABE6
0x18000af3a  xor     edi, edi
0x18000af3c  test    esi, esi
0x18000af3e  jz      loc_18000ABE6
0x18000af44  mov     rcx, [r14+rdi*8]
0x18000af48  test    rcx, rcx
0x18000af4b  jz      short loc_18000AF61
0x18000af4d  mov     rax, [rcx]
0x18000af50  mov     rax, [rax+10h]
0x18000af54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af59  mov     qword ptr [r14+rdi*8], 0
0x18000af61  inc     edi
0x18000af63  cmp     edi, esi
0x18000af65  jb      short loc_18000AF44
0x18000af67  jmp     loc_18000ABE6
```
