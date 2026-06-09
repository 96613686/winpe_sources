# COSKPredictionManager::UpdatePredictionKeys(void)

- ea: `0x14001acc0`
- end: `0x14001b060`
- name: `?UpdatePredictionKeys@COSKPredictionManager@@AEAAXXZ`
- size: `928`
- prototype: `void __fastcall(COSKPredictionManager *__hidden this)`
- caller_count: `2`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14001a4d8`
- `0x14001a894`

## callees

- `0x140005b50`
- `0x14000dd8c`
- `0x14000df60`
- `0x14000f8f4`
- `0x14000f93c`
- `0x140019e34`
- `0x14001acc0`
- `0x14001b068`
- `0x140025d70`
- `0x140027010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x14001ae86`
- `OLEAUT32!__imp_SysAllocString` at `0x14001ae86`
- `OLEAUT32!__imp_SysFreeString` at `0x14001adc6`
- `OLEAUT32!__imp_SysFreeString` at `0x14001ae78`
- `OLEAUT32!__imp_SysFreeString` at `0x14001af2e`
- `OLEAUT32!__imp_SysFreeString` at `0x14001afb7`
- `OLEAUT32!__imp_SysFreeString` at `0x14001afd3`
- `OLEAUT32!__imp_SysFreeString` at `0x14001b014`
- `OLEAUT32!__imp_SysFreeString` at `0x14001adc6`
- `OLEAUT32!__imp_SysFreeString` at `0x14001ae78`
- `OLEAUT32!__imp_SysFreeString` at `0x14001af2e`
- `OLEAUT32!__imp_SysFreeString` at `0x14001afb7`
- `OLEAUT32!__imp_SysFreeString` at `0x14001afd3`
- `OLEAUT32!__imp_SysFreeString` at `0x14001b014`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall COSKPredictionManager::UpdatePredictionKeys(COSKPredictionManager *this)
{
  const OLECHAR *v2; // rsi
  int v3; // edi
  int v4; // edx
  int v5; // ecx
  int v6; // r8d
  int i; // edx
  int v8; // ecx
  OLECHAR *v9; // rax
  int v10; // r8d
  int v11; // edi
  PVOID v12; // rcx
  __int64 v13; // r8
  __int64 v14; // [rsp+40h] [rbp-68h] BYREF
  BSTR bstrString; // [rsp+48h] [rbp-60h] BYREF
  int v16; // [rsp+50h] [rbp-58h] BYREF
  BSTR v17; // [rsp+58h] [rbp-50h] BYREF
  ATL::CAtlException *v18; // [rsp+60h] [rbp-48h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v19; // [rsp+68h] [rbp-40h] BYREF

  try
  {
    v2 = (const OLECHAR *)((char *)this + 32);
    ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v17, (const unsigned __int16 *)this + 16);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_8ca0bf681196307d479db2488c079cf4_Traceguids, v2);
    if ( (*(int (__fastcall **)(_QWORD, BSTR, _QWORD))(**((_QWORD **)this + 39) + 32LL))(*((_QWORD *)this + 39), v17, 0) < 0 )
      goto LABEL_39;
    v14 = 0;
    v19.Ptr = 0;
    if ( (*(int (__fastcall **)(_QWORD, __int64 *, struct _EVENT_DATA_DESCRIPTOR *))(**((_QWORD **)this + 39) + 64LL))(
           *((_QWORD *)this + 39),
           &v14,
           &v19) < 0 )
    {
LABEL_38:
      ATL::CComPtrBase<ITPLangMod>::~CComPtrBase<ITPLangMod>(&v14);
LABEL_39:
      SysFreeString(v17);
      goto LABEL_50;
    }
    v3 = 0;
    COSKPredictionManager::ClearPredictionKeysText(this, 0);
    bstrString = 0;
    v16 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 40LL))(v14);
    do
    {
      if ( (*(unsigned int (__fastcall **)(__int64, BSTR *, int *))(*(_QWORD *)v14 + 32LL))(v14, &bstrString, &v16) )
        break;
      SysFreeString(bstrString);
      ++v3;
    }
    while ( *(_DWORD *)this != v3 );
    if ( !v3 )
    {
      v4 = *((_DWORD *)this + 81);
      if ( v4 <= 0 )
        goto LABEL_30;
      v5 = *((_DWORD *)this + 7);
      if ( v4 >= v5 - 1 )
        goto LABEL_30;
      v6 = v4 + 1;
      for ( i = 0; i < v5 - v6; v5 = *((_DWORD *)this + 7) )
      {
        *((_WORD *)this + i + 16) = *((_WORD *)this + i + v6 + 16);
        ++i;
      }
      v8 = v5 - v6;
      *((_DWORD *)this + 7) = v8;
      *((_WORD *)this + v8 + 16) = 0;
      *((_DWORD *)this + 81) = 0;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          22,
          (unsigned int)WPP_8ca0bf681196307d479db2488c079cf4_Traceguids,
          (_DWORD)v2,
          *((_DWORD *)this + 7));
      v9 = v17;
      if ( v2 != v17 )
      {
        SysFreeString(v17);
        if ( v2 )
        {
          v9 = SysAllocString(v2);
          v17 = v9;
          if ( !v9 )
            ATL::AtlThrowImpl(-2147024882);
        }
        else
        {
          v9 = 0;
          v17 = 0;
        }
      }
      if ( (*(int (__fastcall **)(_QWORD, OLECHAR *, _QWORD))(**((_QWORD **)this + 39) + 32LL))(
             *((_QWORD *)this + 39),
             v9,
             0) < 0 )
        goto LABEL_30;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 40LL))(v14);
      if ( (*(int (__fastcall **)(_QWORD, __int64 *, struct _EVENT_DATA_DESCRIPTOR *))(**((_QWORD **)this + 39) + 64LL))(
             *((_QWORD *)this + 39),
             &v14,
             &v19) < 0 )
        goto LABEL_30;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 40LL))(v14);
      do
      {
        if ( (*(unsigned int (__fastcall **)(__int64, BSTR *, int *))(*(_QWORD *)v14 + 32LL))(v14, &bstrString, &v16) )
          break;
        SysFreeString(bstrString);
        ++v3;
      }
      while ( *(_DWORD *)this != v3 );
    }
    if ( v3 >= 5 )
    {
      v10 = 3;
      if ( v3 >= 7 )
        v10 = *((_DWORD *)this + 1);
LABEL_33:
      *((_DWORD *)this + 2) = v10;
      (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 37) + 304LL))(
        *((_QWORD *)this + 37),
        (unsigned int)v3);
      v11 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 40LL))(v14);
      while ( !(*(unsigned int (__fastcall **)(__int64, BSTR *, int *))(*(_QWORD *)v14 + 32LL))(v14, &bstrString, &v16) )
      {
        if ( *(_DWORD *)this == v11 )
        {
          SysFreeString(bstrString);
          break;
        }
        (*(void (__fastcall **)(_QWORD, BSTR, __int64))(**((_QWORD **)this + 37) + 288LL))(
          *((_QWORD *)this + 37),
          bstrString,
          10);
        SysFreeString(bstrString);
        ++v11;
      }
      *((_DWORD *)this + 72) = v11;
      goto LABEL_38;
    }
    v10 = v3;
    if ( v3 > 0 )
      goto LABEL_33;
LABEL_30:
    v10 = 1;
    goto LABEL_33;
  }
  catch ( ATL::CAtlException *v18 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        23,
        WPP_8ca0bf681196307d479db2488c079cf4_Traceguids,
        *(unsigned int *)v18);
  }
LABEL_50:
  if ( (Microsoft_Windows_oskEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer((__int64)v12, (const EVENT_DESCRIPTOR *)ShowPredictions_Stop, v13, 1u, &v19);
}

```

## disassembly

```asm
0x14001acc0  push    rbx
0x14001acc2  push    rsi
0x14001acc3  push    rdi
0x14001acc4  push    r15
0x14001acc6  sub     rsp, 88h
0x14001accd  mov     rax, cs:__security_cookie
0x14001acd4  xor     rax, rsp
0x14001acd7  mov     [rsp+0A8h+var_30], rax
0x14001acdc  mov     rbx, rcx
0x14001acdf  lea     rsi, [rcx+20h]
0x14001ace3  mov     rdx, rsi; unsigned __int16 *
0x14001ace6  lea     rcx, [rsp+0A8h+var_50]; this
0x14001aceb  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x14001acf0  nop
0x14001acf1  lea     r15, WPP_GLOBAL_Control
0x14001acf8  mov     rcx, cs:WPP_GLOBAL_Control
0x14001acff  cmp     rcx, r15
0x14001ad02  jz      short loc_14001AD22
0x14001ad04  test    byte ptr [rcx+1Ch], 10h
0x14001ad08  jz      short loc_14001AD22
0x14001ad0a  mov     edx, 15h
0x14001ad0f  mov     r9, rsi
0x14001ad12  lea     r8, WPP_8ca0bf681196307d479db2488c079cf4_Traceguids
0x14001ad19  mov     rcx, [rcx+10h]
0x14001ad1d  call    WPP_SF_S
0x14001ad22  mov     rcx, [rbx+138h]
0x14001ad29  mov     rax, [rcx]
0x14001ad2c  xor     r8d, r8d
0x14001ad2f  mov     rdx, [rsp+0A8h+var_50]
0x14001ad34  mov     rax, [rax+20h]
0x14001ad38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001ad3d  test    eax, eax
0x14001ad3f  js      loc_14001AFCE
0x14001ad45  mov     [rsp+0A8h+var_68], 0
0x14001ad4e  mov     qword ptr [rsp+0A8h+var_40], 0
0x14001ad57  mov     rcx, [rbx+138h]
0x14001ad5e  mov     rax, [rcx]
0x14001ad61  lea     r8, [rsp+0A8h+var_40]
0x14001ad66  lea     rdx, [rsp+0A8h+var_68]
0x14001ad6b  mov     rax, [rax+40h]
0x14001ad6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001ad74  test    eax, eax
0x14001ad76  js      loc_14001AFC3
0x14001ad7c  xor     edi, edi
0x14001ad7e  xor     edx, edx; bool
0x14001ad80  mov     rcx, rbx; this
0x14001ad83  call    ?ClearPredictionKeysText@COSKPredictionManager@@AEAAX_N@Z; COSKPredictionManager::ClearPredictionKeysText(bool)
0x14001ad88  mov     [rsp+0A8h+bstrString], rdi
0x14001ad8d  mov     [rsp+0A8h+var_58], edi
0x14001ad91  mov     rcx, [rsp+0A8h+var_68]
0x14001ad96  mov     rax, [rcx]
0x14001ad99  mov     rax, [rax+28h]
0x14001ad9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001ada2  mov     rcx, [rsp+0A8h+var_68]
0x14001ada7  mov     rax, [rcx]
0x14001adaa  lea     r8, [rsp+0A8h+var_58]
0x14001adaf  lea     rdx, [rsp+0A8h+bstrString]
0x14001adb4  mov     rax, [rax+20h]
0x14001adb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001adbd  test    eax, eax
0x14001adbf  jnz     short loc_14001ADD2
0x14001adc1  mov     rcx, [rsp+0A8h+bstrString]; bstrString
0x14001adc6  call    cs:__imp_SysFreeString
0x14001adcc  inc     edi
0x14001adce  cmp     [rbx], edi
0x14001add0  jnz     short loc_14001ADA2
0x14001add2  test    edi, edi
0x14001add4  jnz     loc_14001AF3A
0x14001adda  mov     edx, [rbx+144h]
0x14001ade0  test    edx, edx
0x14001ade2  jle     loc_14001AF46
0x14001ade8  mov     ecx, [rbx+1Ch]
0x14001adeb  lea     eax, [rcx-1]
0x14001adee  cmp     edx, eax
0x14001adf0  jge     loc_14001AF46
0x14001adf6  lea     r8d, [rdx+1]
0x14001adfa  xor     edx, edx
0x14001adfc  mov     eax, ecx
0x14001adfe  sub     eax, r8d
0x14001ae01  test    eax, eax
0x14001ae03  jle     short loc_14001AE26
0x14001ae05  lea     eax, [rdx+r8]
0x14001ae09  cdqe
0x14001ae0b  movsxd  rcx, edx
0x14001ae0e  movzx   eax, word ptr [rbx+rax*2+20h]
0x14001ae13  mov     [rbx+rcx*2+20h], ax
0x14001ae18  inc     edx
0x14001ae1a  mov     ecx, [rbx+1Ch]
0x14001ae1d  mov     eax, ecx
0x14001ae1f  sub     eax, r8d
0x14001ae22  cmp     edx, eax
0x14001ae24  jl      short loc_14001AE05
0x14001ae26  sub     ecx, r8d
0x14001ae29  mov     [rbx+1Ch], ecx
0x14001ae2c  movsxd  rcx, ecx
0x14001ae2f  xor     eax, eax
0x14001ae31  mov     [rbx+rcx*2+20h], ax
0x14001ae36  mov     [rbx+144h], eax
0x14001ae3c  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ae43  cmp     rcx, r15
0x14001ae46  jz      short loc_14001AE6B
0x14001ae48  test    byte ptr [rcx+1Ch], 10h
0x14001ae4c  jz      short loc_14001AE6B
0x14001ae4e  lea     edx, [rax+16h]
0x14001ae51  mov     eax, [rbx+1Ch]
0x14001ae54  mov     dword ptr [rsp+0A8h+var_88], eax
0x14001ae58  mov     r9, rsi
0x14001ae5b  lea     r8, WPP_8ca0bf681196307d479db2488c079cf4_Traceguids
0x14001ae62  mov     rcx, [rcx+10h]
0x14001ae66  call    WPP_SF_Sd
0x14001ae6b  mov     rax, [rsp+0A8h+var_50]
0x14001ae70  cmp     rsi, rax
0x14001ae73  jz      short loc_14001AEA7
0x14001ae75  mov     rcx, rax; bstrString
0x14001ae78  call    cs:__imp_SysFreeString
0x14001ae7e  test    rsi, rsi
0x14001ae81  jz      short loc_14001AEA0
0x14001ae83  mov     rcx, rsi; psz
0x14001ae86  call    cs:__imp_SysAllocString
0x14001ae8c  mov     [rsp+0A8h+var_50], rax
0x14001ae91  test    rax, rax
0x14001ae94  jnz     short loc_14001AEA7
0x14001ae96  mov     ecx, 8007000Eh; int
0x14001ae9b  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x14001aea0  xor     eax, eax
0x14001aea2  mov     [rsp+0A8h+var_50], rax
0x14001aea7  mov     rcx, [rbx+138h]
0x14001aeae  mov     rdx, [rcx]
0x14001aeb1  mov     r9, [rdx+20h]
0x14001aeb5  xor     r8d, r8d
0x14001aeb8  mov     rdx, rax
0x14001aebb  mov     rax, r9
0x14001aebe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001aec3  test    eax, eax
0x14001aec5  js      short loc_14001AF46
0x14001aec7  mov     rcx, [rsp+0A8h+var_68]
0x14001aecc  mov     rax, [rcx]
0x14001aecf  mov     rax, [rax+28h]
0x14001aed3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001aed8  mov     rcx, [rbx+138h]
0x14001aedf  mov     rax, [rcx]
0x14001aee2  lea     r8, [rsp+0A8h+var_40]
0x14001aee7  lea     rdx, [rsp+0A8h+var_68]
0x14001aeec  mov     rax, [rax+40h]
0x14001aef0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001aef5  test    eax, eax
0x14001aef7  js      short loc_14001AF46
0x14001aef9  mov     rcx, [rsp+0A8h+var_68]
0x14001aefe  mov     rax, [rcx]
0x14001af01  mov     rax, [rax+28h]
0x14001af05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001af0a  mov     rcx, [rsp+0A8h+var_68]
0x14001af0f  mov     rax, [rcx]
0x14001af12  lea     r8, [rsp+0A8h+var_58]
0x14001af17  lea     rdx, [rsp+0A8h+bstrString]
0x14001af1c  mov     rax, [rax+20h]
0x14001af20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001af25  test    eax, eax
0x14001af27  jnz     short loc_14001AF3A
0x14001af29  mov     rcx, [rsp+0A8h+bstrString]; bstrString
0x14001af2e  call    cs:__imp_SysFreeString
0x14001af34  inc     edi
0x14001af36  cmp     [rbx], edi
0x14001af38  jnz     short loc_14001AF0A
0x14001af3a  cmp     edi, 5
0x14001af3d  jge     short loc_14001AF4E
0x14001af3f  test    edi, edi
0x14001af41  mov     r8d, edi
0x14001af44  jg      short loc_14001AF5D
0x14001af46  mov     r8d, 1
0x14001af4c  jmp     short loc_14001AF5D
0x14001af4e  cmp     edi, 7
0x14001af51  mov     r8d, 3
0x14001af57  jl      short loc_14001AF5D
0x14001af59  mov     r8d, [rbx+4]
0x14001af5d  mov     rsi, rbx
0x14001af60  mov     [rbx+8], r8d
0x14001af64  mov     rcx, [rbx+128h]
0x14001af6b  mov     rax, [rcx]
0x14001af6e  mov     edx, edi
0x14001af70  mov     rax, [rax+130h]
0x14001af77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001af7c  xor     edi, edi
0x14001af7e  mov     rcx, [rsp+0A8h+var_68]
0x14001af83  mov     rax, [rcx]
0x14001af86  mov     rax, [rax+28h]
0x14001af8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001af8f  mov     rcx, [rsp+0A8h+var_68]
0x14001af94  mov     rax, [rcx]
0x14001af97  lea     r8, [rsp+0A8h+var_58]
0x14001af9c  lea     rdx, [rsp+0A8h+bstrString]
0x14001afa1  mov     rax, [rax+20h]
0x14001afa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001afaa  test    eax, eax
0x14001afac  jnz     short loc_14001AFBD
0x14001afae  cmp     [rbx], edi
0x14001afb0  jnz     short loc_14001AFDC
0x14001afb2  mov     rcx, [rsp+0A8h+bstrString]; bstrString
0x14001afb7  call    cs:__imp_SysFreeString
0x14001afbd  mov     [rbx+120h], edi
0x14001afc3  lea     rcx, [rsp+0A8h+var_68]
0x14001afc8  call    ??1?$CComPtrBase@UITPLangMod@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITPLangMod>::~CComPtrBase<ITPLangMod>(void)
0x14001afcd  nop
0x14001afce  mov     rcx, [rsp+0A8h+var_50]; bstrString
0x14001afd3  call    cs:__imp_SysFreeString
0x14001afd9  nop
0x14001afda  jmp     short loc_14001B021
0x14001afdc  mov     rcx, [rbx+128h]
0x14001afe3  mov     eax, edi
0x14001afe5  cdq
0x14001afe6  idiv    dword ptr [rsi+8]
0x14001afe9  mov     r8, [rcx]
0x14001afec  mov     r10, [r8+120h]
0x14001aff3  mov     [rsp+0A8h+var_80], edx
0x14001aff7  mov     dword ptr [rsp+0A8h+var_88], eax
0x14001affb  xor     r9d, r9d
0x14001affe  lea     r8d, [r9+0Ah]
0x14001b002  mov     rdx, [rsp+0A8h+bstrString]
0x14001b007  mov     rax, r10
0x14001b00a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001b00f  mov     rcx, [rsp+0A8h+bstrString]; bstrString
0x14001b014  call    cs:__imp_SysFreeString
0x14001b01a  inc     edi
0x14001b01c  jmp     loc_14001AF8F
0x14001b021  test    cs:Microsoft_Windows_oskEnableBits, 1
0x14001b028  jz      short loc_14001B046
0x14001b02a  lea     rax, [rsp+0A8h+var_40]
0x14001b02f  mov     [rsp+0A8h+var_88], rax
0x14001b034  mov     r9d, 1
0x14001b03a  lea     rdx, ShowPredictions_Stop
0x14001b041  call    McGenEventWrite_EventWriteTransfer
0x14001b046  mov     rcx, [rsp+0A8h+var_30]
0x14001b04b  xor     rcx, rsp; StackCookie
0x14001b04e  call    __security_check_cookie
0x14001b053  add     rsp, 88h
0x14001b05a  pop     r15
0x14001b05c  pop     rdi
0x14001b05d  pop     rsi
0x14001b05e  pop     rbx
0x14001b05f  retn
```
