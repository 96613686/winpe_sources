# LpGenerateProfileXml

- ea: `0x180032f7c`
- end: `0x1800331bc`
- name: `LpGenerateProfileXml`
- size: `576`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `7`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000ca8c`
- `0x18000e6a8`
- `0x18000e948`
- `0x18000ec24`
- `0x18001a22c`
- `0x180033de4`
- `0x180037314`

## callees

- `0x18000a9c0`
- `0x18000c230`
- `0x18000c4b0`
- `0x1800328f8`
- `0x180032ee0`
- `0x180032f7c`
- `0x18003a9e0`
- `0x18003af30`
- `0x18003b830`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800331a2`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800331a2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall LpGenerateProfileXml(__int64 a1, unsigned __int16 **a2)
{
  struct _LIST_ENTRY *v4; // rcx
  unsigned int ProfileNode; // eax
  unsigned int v6; // edi
  __int64 v7; // rdx
  __int64 v8; // r9
  int v10; // [rsp+50h] [rbp+8h] BYREF
  struct IXMLDOMDocument2 *v11; // [rsp+60h] [rbp+18h] BYREF

  v10 = 0;
  v11 = 0;
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 26, WPP_25f5f272669b3cc70b9a4d690e9b67ad_Traceguids);
    v4 = WPP_GLOBAL_Control;
  }
  if ( a1 && *(_DWORD *)(a1 + 536) == 5304834 && *(_QWORD *)(a1 + 552) )
  {
    ProfileNode = CXcSmartCoInit::Init((CXcSmartCoInit *)&v10);
    v6 = ProfileNode;
    if ( ProfileNode )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        goto LABEL_44;
      if ( !BYTE1(WPP_GLOBAL_Control[1].Blink) || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
        goto LABEL_40;
      v7 = 28;
    }
    else
    {
      ProfileNode = LpCreateXmlDoc(0, 0, &v11);
      v6 = ProfileNode;
      if ( ProfileNode )
      {
        v4 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
          goto LABEL_44;
        if ( !BYTE1(WPP_GLOBAL_Control[1].Blink) || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
          goto LABEL_40;
        v7 = 29;
      }
      else
      {
        ProfileNode = XcAddXmlPI(v11);
        v6 = ProfileNode;
        if ( ProfileNode )
        {
          v4 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
            goto LABEL_44;
          if ( !BYTE1(WPP_GLOBAL_Control[1].Blink) || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
            goto LABEL_40;
          v7 = 30;
        }
        else
        {
          ProfileNode = LpGenerateProfileNode(a1, v11);
          v6 = ProfileNode;
          if ( ProfileNode )
          {
            v4 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
              goto LABEL_44;
            if ( !BYTE1(WPP_GLOBAL_Control[1].Blink) || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
              goto LABEL_40;
            v7 = 31;
          }
          else
          {
            ProfileNode = XcGetNodeXmlIndented((struct IXMLDOMNode *)v11, a2);
            v6 = ProfileNode;
            if ( !ProfileNode )
            {
LABEL_39:
              v4 = WPP_GLOBAL_Control;
              goto LABEL_40;
            }
            v4 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
              goto LABEL_44;
            if ( !BYTE1(WPP_GLOBAL_Control[1].Blink) || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
              goto LABEL_40;
            v7 = 32;
          }
        }
      }
    }
    v8 = ProfileNode;
LABEL_38:
    WPP_SF_d(v4[1].Flink, v7, WPP_25f5f272669b3cc70b9a4d690e9b67ad_Traceguids, v8);
    goto LABEL_39;
  }
  v6 = 87;
  if ( v4 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
    goto LABEL_44;
  if ( BYTE1(v4[1].Blink) && (BYTE4(v4[1].Blink) & 1) != 0 )
  {
    v7 = 27;
    v8 = 87;
    goto LABEL_38;
  }
LABEL_40:
  if ( v4 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && BYTE1(v4[1].Blink) >= 4u && (BYTE4(v4[1].Blink) & 1) != 0 )
    WPP_SF_d(v4[1].Flink, 33, WPP_25f5f272669b3cc70b9a4d690e9b67ad_Traceguids, v6);
LABEL_44:
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>((__int64 *)&v11);
  if ( v10 )
    CoUninitialize();
  return v6;
}

```

## disassembly

```asm
0x180032f7c  mov     [rsp+arg_8], rbp
0x180032f81  push    rsi
0x180032f82  push    rdi
0x180032f83  push    r12
0x180032f85  push    r13
0x180032f87  push    r14
0x180032f89  sub     rsp, 20h
0x180032f8d  mov     rbp, rdx
0x180032f90  mov     rsi, rcx
0x180032f93  mov     [rsp+48h+arg_0], 0
0x180032f9b  mov     [rsp+48h+arg_10], 0
0x180032fa4  lea     r12, WPP_GLOBAL_Control
0x180032fab  mov     r14b, 1
0x180032fae  lea     r13, WPP_25f5f272669b3cc70b9a4d690e9b67ad_Traceguids
0x180032fb5  mov     rcx, cs:WPP_GLOBAL_Control
0x180032fbc  cmp     rcx, r12
0x180032fbf  jz      short loc_180032FE5
0x180032fc1  cmp     byte ptr [rcx+19h], 4
0x180032fc5  jb      short loc_180032FE5
0x180032fc7  test    [rcx+1Ch], r14b
0x180032fcb  jz      short loc_180032FE5
0x180032fcd  mov     edx, 1Ah
0x180032fd2  mov     r8, r13
0x180032fd5  mov     rcx, [rcx+10h]
0x180032fd9  call    WPP_SF_
0x180032fde  mov     rcx, cs:WPP_GLOBAL_Control
0x180032fe5  test    rsi, rsi
0x180032fe8  jz      loc_18003313B
0x180032fee  cmp     dword ptr [rsi+218h], 50F202h
0x180032ff8  jnz     loc_18003313B
0x180032ffe  cmp     qword ptr [rsi+228h], 0
0x180033006  jz      loc_18003313B
0x18003300c  lea     rcx, [rsp+48h+arg_0]; this
0x180033011  call    ?Init@CXcSmartCoInit@@QEAAKXZ; CXcSmartCoInit::Init(void)
0x180033016  mov     edi, eax
0x180033018  test    eax, eax
0x18003301a  jz      short loc_18003304D
0x18003301c  mov     rcx, cs:WPP_GLOBAL_Control
0x180033023  cmp     rcx, r12
0x180033026  jz      loc_180033190
0x18003302c  cmp     [rcx+19h], r14b
0x180033030  jb      loc_18003316A
0x180033036  test    [rcx+1Ch], r14b
0x18003303a  jz      loc_18003316A
0x180033040  mov     edx, 1Ch
0x180033045  mov     r9d, eax
0x180033048  jmp     loc_180033157
0x18003304d  lea     r8, [rsp+48h+arg_10]
0x180033052  xor     edx, edx
0x180033054  xor     ecx, ecx
0x180033056  call    LpCreateXmlDoc
0x18003305b  mov     edi, eax
0x18003305d  test    eax, eax
0x18003305f  jz      short loc_18003308C
0x180033061  mov     rcx, cs:WPP_GLOBAL_Control
0x180033068  cmp     rcx, r12
0x18003306b  jz      loc_180033190
0x180033071  cmp     [rcx+19h], r14b
0x180033075  jb      loc_18003316A
0x18003307b  test    [rcx+1Ch], r14b
0x18003307f  jz      loc_18003316A
0x180033085  mov     edx, 1Dh
0x18003308a  jmp     short loc_180033045
0x18003308c  mov     rcx, [rsp+48h+arg_10]; struct IXMLDOMDocument2 *
0x180033091  call    ?XcAddXmlPI@@YAKPEAUIXMLDOMDocument2@@@Z; XcAddXmlPI(IXMLDOMDocument2 *)
0x180033096  mov     edi, eax
0x180033098  test    eax, eax
0x18003309a  jz      short loc_1800330CA
0x18003309c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800330a3  cmp     rcx, r12
0x1800330a6  jz      loc_180033190
0x1800330ac  cmp     [rcx+19h], r14b
0x1800330b0  jb      loc_18003316A
0x1800330b6  test    [rcx+1Ch], r14b
0x1800330ba  jz      loc_18003316A
0x1800330c0  mov     edx, 1Eh
0x1800330c5  jmp     loc_180033045
0x1800330ca  mov     r8, [rsp+48h+arg_10]
0x1800330cf  mov     rdx, r8
0x1800330d2  mov     rcx, rsi
0x1800330d5  call    LpGenerateProfileNode
0x1800330da  mov     edi, eax
0x1800330dc  test    eax, eax
0x1800330de  jz      short loc_180033106
0x1800330e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800330e7  cmp     rcx, r12
0x1800330ea  jz      loc_180033190
0x1800330f0  cmp     [rcx+19h], r14b
0x1800330f4  jb      short loc_18003316A
0x1800330f6  test    [rcx+1Ch], r14b
0x1800330fa  jz      short loc_18003316A
0x1800330fc  mov     edx, 1Fh
0x180033101  jmp     loc_180033045
0x180033106  mov     rdx, rbp; unsigned __int16 **
0x180033109  mov     rcx, [rsp+48h+arg_10]; struct IXMLDOMNode *
0x18003310e  call    ?XcGetNodeXmlIndented@@YAKPEAUIXMLDOMNode@@PEAPEAG@Z; XcGetNodeXmlIndented(IXMLDOMNode *,ushort * *)
0x180033113  mov     edi, eax
0x180033115  test    eax, eax
0x180033117  jz      short loc_180033163
0x180033119  mov     rcx, cs:WPP_GLOBAL_Control
0x180033120  cmp     rcx, r12
0x180033123  jz      short loc_180033190
0x180033125  cmp     [rcx+19h], r14b
0x180033129  jb      short loc_18003316A
0x18003312b  test    [rcx+1Ch], r14b
0x18003312f  jz      short loc_18003316A
0x180033131  mov     edx, 20h ; ' '
0x180033136  jmp     loc_180033045
0x18003313b  mov     edi, 57h ; 'W'
0x180033140  cmp     rcx, r12
0x180033143  jz      short loc_180033190
0x180033145  cmp     [rcx+19h], r14b
0x180033149  jb      short loc_18003316A
0x18003314b  test    [rcx+1Ch], r14b
0x18003314f  jz      short loc_18003316A
0x180033151  lea     edx, [rdi-3Ch]
0x180033154  mov     r9d, edi
0x180033157  mov     r8, r13
0x18003315a  mov     rcx, [rcx+10h]
0x18003315e  call    WPP_SF_d
0x180033163  mov     rcx, cs:WPP_GLOBAL_Control
0x18003316a  cmp     rcx, r12
0x18003316d  jz      short loc_180033190
0x18003316f  cmp     byte ptr [rcx+19h], 4
0x180033173  jb      short loc_180033190
0x180033175  test    [rcx+1Ch], r14b
0x180033179  jz      short loc_180033190
0x18003317b  mov     edx, 21h ; '!'
0x180033180  mov     r9d, edi
0x180033183  mov     r8, r13
0x180033186  mov     rcx, [rcx+10h]
0x18003318a  call    WPP_SF_d
0x18003318f  nop
0x180033190  lea     rcx, [rsp+48h+arg_10]
0x180033195  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x18003319a  nop
0x18003319b  cmp     [rsp+48h+arg_0], 0
0x1800331a0  jz      short loc_1800331A8
0x1800331a2  call    cs:__imp_CoUninitialize
0x1800331a8  mov     eax, edi
0x1800331aa  mov     rbp, [rsp+48h+arg_8]
0x1800331af  add     rsp, 20h
0x1800331b3  pop     r14
0x1800331b5  pop     r13
0x1800331b7  pop     r12
0x1800331b9  pop     rdi
0x1800331ba  pop     rsi
0x1800331bb  retn
```
