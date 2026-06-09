# UstCommon::CWmiObject::CreateWbemClassObject(IWbemServices *,IWbemContext *,IWbemClassObject * *)

- ea: `0x180027264`
- end: `0x1800273df`
- name: `?CreateWbemClassObject@CWmiObject@UstCommon@@QEAAJPEAUIWbemServices@@PEAUIWbemContext@@PEAPEAUIWbemClassObject@@@Z`
- size: `379`
- prototype: `__int64 __fastcall(UstCommon::CWmiObject *__hidden this, struct IWbemServices *, struct IWbemContext *, struct IWbemClassObject **)`
- caller_count: `6`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001c644`
- `0x18001c700`
- `0x1800229ac`
- `0x180022a5c`
- `0x180025248`
- `0x180025320`

## callees

- `0x180009d50`
- `0x18000f5cc`
- `0x1800140c8`
- `0x18001d484`
- `0x180027264`
- `0x18002c010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall UstCommon::CWmiObject::CreateWbemClassObject(
        UstCommon::CWmiObject *this,
        struct IWbemServices *a2,
        struct IWbemContext *a3,
        struct IWbemClassObject **a4)
{
  int v8; // eax
  int v9; // ebx
  __int64 v10; // rcx
  int v11; // eax
  int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // r9
  __int64 v16; // [rsp+60h] [rbp+8h] BYREF

  *a4 = 0;
  v16 = 0;
  v8 = (*(__int64 (__fastcall **)(UstCommon::CWmiObject *, struct IWbemServices *, struct IWbemContext *, __int64 *))(*(_QWORD *)this + 48LL))(
         this,
         a2,
         a3,
         &v16);
  v9 = v8;
  v10 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
  {
    WPP_SF_SD(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      12,
      (unsigned int)WPP_61fed80e369d3251846e49c329ed71e7_Traceguids,
      *((_QWORD *)this + 9),
      v8);
    v10 = WPP_GLOBAL_Control;
  }
  if ( v9 < 0 )
    goto LABEL_18;
  v11 = (*(__int64 (__fastcall **)(UstCommon::CWmiObject *, struct IWbemServices *, struct IWbemContext *, __int64))(*(_QWORD *)this + 16LL))(
          this,
          a2,
          a3,
          v16);
  v9 = v11;
  v10 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
  {
    WPP_SF_SD(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      13,
      (unsigned int)WPP_61fed80e369d3251846e49c329ed71e7_Traceguids,
      *((_QWORD *)this + 9),
      v11);
    v10 = WPP_GLOBAL_Control;
  }
  if ( v9 < 0 )
  {
    if ( (_UNKNOWN *)v10 == &WPP_GLOBAL_Control )
      goto LABEL_21;
    if ( (*(_BYTE *)(v10 + 28) & 1) == 0 )
      goto LABEL_18;
    v13 = 15;
    v14 = (unsigned int)v9;
    goto LABEL_16;
  }
  v12 = ATL::CComPtrBase<IWbemClassObject>::CopyTo(&v16, a4);
  v9 = v12;
  if ( v12 >= 0 )
  {
LABEL_17:
    v10 = WPP_GLOBAL_Control;
    goto LABEL_18;
  }
  v10 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    goto LABEL_21;
  if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
  {
    v13 = 14;
    v14 = (unsigned int)v12;
LABEL_16:
    WPP_SF_d(*(_QWORD *)(v10 + 16), v13, WPP_61fed80e369d3251846e49c329ed71e7_Traceguids, v14);
    goto LABEL_17;
  }
LABEL_18:
  if ( (_UNKNOWN *)v10 != &WPP_GLOBAL_Control && (*(_BYTE *)(v10 + 28) & 2) != 0 )
    WPP_SF_SD(
      *(_QWORD *)(v10 + 16),
      16,
      (unsigned int)WPP_61fed80e369d3251846e49c329ed71e7_Traceguids,
      *((_QWORD *)this + 9),
      v9);
LABEL_21:
  ATL::CComPtrBase<IOfflineFilesCache>::~CComPtrBase<IOfflineFilesCache>(&v16);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180027264  mov     r11, rsp
0x180027267  mov     [r11+10h], rbx
0x18002726b  mov     [r11+18h], rbp
0x18002726f  push    rsi
0x180027270  push    rdi
0x180027271  push    r12
0x180027273  push    r14
0x180027275  push    r15
0x180027277  sub     rsp, 30h
0x18002727b  mov     rsi, r9
0x18002727e  mov     rbp, r8
0x180027281  mov     r14, rdx
0x180027284  mov     rdi, rcx
0x180027287  mov     qword ptr [r9], 0
0x18002728e  mov     qword ptr [r11+8], 0
0x180027296  mov     rax, [rcx]
0x180027299  lea     r9, [r11+8]
0x18002729d  mov     rax, [rax+30h]
0x1800272a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800272a6  mov     ebx, eax
0x1800272a8  lea     r12, WPP_GLOBAL_Control
0x1800272af  lea     r15, WPP_61fed80e369d3251846e49c329ed71e7_Traceguids
0x1800272b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800272bd  cmp     rcx, r12
0x1800272c0  jz      short loc_1800272E8
0x1800272c2  test    byte ptr [rcx+1Ch], 1
0x1800272c6  jz      short loc_1800272E8
0x1800272c8  mov     edx, 0Ch
0x1800272cd  mov     [rsp+58h+var_38], eax
0x1800272d1  mov     r9, [rdi+48h]
0x1800272d5  mov     r8, r15
0x1800272d8  mov     rcx, [rcx+10h]
0x1800272dc  call    WPP_SF_SD
0x1800272e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800272e8  test    ebx, ebx
0x1800272ea  js      loc_180027397
0x1800272f0  mov     rax, [rdi]
0x1800272f3  mov     r9, [rsp+58h+arg_0]
0x1800272f8  mov     r8, rbp
0x1800272fb  mov     rdx, r14
0x1800272fe  mov     rcx, rdi
0x180027301  mov     rax, [rax+10h]
0x180027305  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002730a  mov     ebx, eax
0x18002730c  mov     rcx, cs:WPP_GLOBAL_Control
0x180027313  cmp     rcx, r12
0x180027316  jz      short loc_18002733E
0x180027318  test    byte ptr [rcx+1Ch], 2
0x18002731c  jz      short loc_18002733E
0x18002731e  mov     edx, 0Dh
0x180027323  mov     [rsp+58h+var_38], eax
0x180027327  mov     r9, [rdi+48h]
0x18002732b  mov     r8, r15
0x18002732e  mov     rcx, [rcx+10h]
0x180027332  call    WPP_SF_SD
0x180027337  mov     rcx, cs:WPP_GLOBAL_Control
0x18002733e  test    ebx, ebx
0x180027340  js      short loc_180027371
0x180027342  mov     rdx, rsi
0x180027345  lea     rcx, [rsp+58h+arg_0]
0x18002734a  call    ?CopyTo@?$CComPtrBase@UIWbemClassObject@@@ATL@@QEAAJPEAPEAUIWbemClassObject@@@Z; ATL::CComPtrBase<IWbemClassObject>::CopyTo(IWbemClassObject * *)
0x18002734f  mov     ebx, eax
0x180027351  test    eax, eax
0x180027353  jns     short loc_180027390
0x180027355  mov     rcx, cs:WPP_GLOBAL_Control
0x18002735c  cmp     rcx, r12
0x18002735f  jz      short loc_1800273BC
0x180027361  test    byte ptr [rcx+1Ch], 1
0x180027365  jz      short loc_180027397
0x180027367  mov     edx, 0Eh
0x18002736c  mov     r9d, eax
0x18002736f  jmp     short loc_180027384
0x180027371  cmp     rcx, r12
0x180027374  jz      short loc_1800273BC
0x180027376  test    byte ptr [rcx+1Ch], 1
0x18002737a  jz      short loc_180027397
0x18002737c  mov     edx, 0Fh
0x180027381  mov     r9d, ebx
0x180027384  mov     r8, r15
0x180027387  mov     rcx, [rcx+10h]
0x18002738b  call    WPP_SF_d
0x180027390  mov     rcx, cs:WPP_GLOBAL_Control
0x180027397  cmp     rcx, r12
0x18002739a  jz      short loc_1800273BC
0x18002739c  test    byte ptr [rcx+1Ch], 2
0x1800273a0  jz      short loc_1800273BC
0x1800273a2  mov     edx, 10h
0x1800273a7  mov     [rsp+58h+var_38], ebx
0x1800273ab  mov     r9, [rdi+48h]
0x1800273af  mov     r8, r15
0x1800273b2  mov     rcx, [rcx+10h]
0x1800273b6  call    WPP_SF_SD
0x1800273bb  nop
0x1800273bc  lea     rcx, [rsp+58h+arg_0]
0x1800273c1  call    ??1?$CComPtrBase@UIOfflineFilesCache@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IOfflineFilesCache>::~CComPtrBase<IOfflineFilesCache>(void)
0x1800273c6  mov     eax, ebx
0x1800273c8  mov     rbx, [rsp+58h+arg_8]
0x1800273cd  mov     rbp, [rsp+58h+arg_10]
0x1800273d2  add     rsp, 30h
0x1800273d6  pop     r15
0x1800273d8  pop     r14
0x1800273da  pop     r12
0x1800273dc  pop     rdi
0x1800273dd  pop     rsi
0x1800273de  retn
```
