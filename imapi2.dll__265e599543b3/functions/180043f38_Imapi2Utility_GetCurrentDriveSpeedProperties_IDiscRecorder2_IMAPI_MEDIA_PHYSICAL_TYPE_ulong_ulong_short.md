# Imapi2Utility::GetCurrentDriveSpeedProperties(IDiscRecorder2 *,_IMAPI_MEDIA_PHYSICAL_TYPE,ulong *,ulong *,short *)

- ea: `0x180043f38`
- end: `0x180044162`
- name: `?GetCurrentDriveSpeedProperties@Imapi2Utility@@YAJPEAUIDiscRecorder2@@W4_IMAPI_MEDIA_PHYSICAL_TYPE@@PEAK2PEAF@Z`
- size: `554`
- prototype: `int(Imapi2Utility *__hidden this, struct IDiscRecorder2 *, enum _IMAPI_MEDIA_PHYSICAL_TYPE, unsigned int *, unsigned int *, __int16 *)`
- caller_count: `10`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x180021610`
- `0x1800216c0`
- `0x180026638`
- `0x180026860`
- `0x180031530`
- `0x1800315e0`
- `0x18003abb0`
- `0x18003ac60`
- `0x180042ae0`
- `0x180047cd8`

## callees

- `0x18000cae8`
- `0x1800140f4`
- `0x180014180`
- `0x180016778`
- `0x180043a90`
- `0x180043bb4`
- `0x180043f38`
- `0x180048108`
- `0x18004a010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1800440d0`
- `ole32!CoTaskMemFree` at `0x1800440d0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Imapi2Utility::GetCurrentDriveSpeedProperties(
        Imapi2Utility *this,
        struct IDiscRecorder2 *a2,
        unsigned int *a3,
        _IMAPI_MEDIA_PHYSICAL_TYPE *a4,
        unsigned int *a5)
{
  unsigned int v7; // edi
  struct IDiscRecorder2Ex *v9; // rdx
  int CurrentDriveSpeed; // ebx
  unsigned int *v11; // r9
  unsigned int *v12; // r9
  enum _IMAPI_MEDIA_PHYSICAL_TYPE v13; // edx
  unsigned int v14; // r8d
  unsigned int *v15; // rdi
  char v16; // al
  Imapi2Utility *v18; // [rsp+30h] [rbp-18h] BYREF
  LPVOID pv[2]; // [rsp+38h] [rbp-10h] BYREF
  _IMAPI_MEDIA_PHYSICAL_TYPE v20; // [rsp+80h] [rbp+38h] BYREF

  v7 = (unsigned int)a2;
  v20 = IMAPI_MEDIA_TYPE_UNKNOWN;
  v18 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 93, &WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids);
  }
  CurrentDriveSpeed = (**(__int64 (__fastcall ***)(Imapi2Utility *, GUID *, Imapi2Utility **))this)(
                        this,
                        &GUID_27354132_7f64_5b0f_8f00_5d77afbe261e,
                        &v18);
  if ( CurrentDriveSpeed >= 0 )
  {
    LOBYTE(v9) = 1;
    CurrentDriveSpeed = Imapi2Utility::GetCurrentDriveSpeed(v18, v9, (unsigned __int8)&v20, v11);
    if ( CurrentDriveSpeed < 0
      || (v13 = v20,
          *a4 = v20,
          CurrentDriveSpeed = Imapi2Utility::FuzzyConvert_KBps2SectorsPerSecond(
                                (Imapi2Utility *)v7,
                                v13,
                                (unsigned int)a3,
                                v12),
          CurrentDriveSpeed < 0) )
    {
LABEL_28:
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          97,
          &WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids,
          (unsigned int)CurrentDriveSpeed);
      }
      goto LABEL_32;
    }
    pv[0] = 0;
    v20 = IMAPI_MEDIA_TYPE_UNKNOWN;
    CurrentDriveSpeed = (*(__int64 (__fastcall **)(Imapi2Utility *, __int64, _QWORD, LPVOID *, _IMAPI_MEDIA_PHYSICAL_TYPE *))(*(_QWORD *)v18 + 104LL))(
                          v18,
                          42,
                          0,
                          pv,
                          &v20);
    v15 = a5;
    if ( CurrentDriveSpeed >= 0 )
    {
      CurrentDriveSpeed = Imapi2Utility::ValidateCapabilitiesModePageLength(
                            (Imapi2Utility *)pv[0],
                            (struct _CDVD_CAPABILITIES_PAGE *const)(unsigned int)v20,
                            v14);
      if ( CurrentDriveSpeed >= 0 )
      {
        if ( *((_BYTE *)pv[0] + 1) < 0x1Cu )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 95, &WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids);
          }
        }
        else
        {
          v16 = *((_BYTE *)pv[0] + 27) & 3;
          if ( v16 )
          {
            if ( v16 == 1 )
            {
              *(_WORD *)v15 = 1;
              goto LABEL_23;
            }
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                94,
                &WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids,
                *((_BYTE *)pv[0] + 27) & 3);
            }
          }
        }
        *(_WORD *)v15 = 0;
      }
    }
LABEL_23:
    CoTaskMemFree(pv[0]);
    if ( CurrentDriveSpeed >= 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_ddD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          96,
          &WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids,
          *a3,
          *a4,
          *(__int16 *)v15);
      }
      goto LABEL_32;
    }
    goto LABEL_28;
  }
LABEL_32:
  ATL::CComPtrBase<IDiscRecorder2Ex>::~CComPtrBase<IDiscRecorder2Ex>(&v18);
  return (unsigned int)CurrentDriveSpeed;
}

```

## disassembly

```asm
0x180043f38  push    rbp
0x180043f3a  push    rbx
0x180043f3b  push    rsi
0x180043f3c  push    rdi
0x180043f3d  push    r13
0x180043f3f  push    r14
0x180043f41  mov     rbp, rsp
0x180043f44  sub     rsp, 48h
0x180043f48  mov     rsi, r9
0x180043f4b  mov     r14, r8
0x180043f4e  mov     edi, edx
0x180043f50  mov     rbx, rcx
0x180043f53  mov     [rbp+arg_0], 0
0x180043f5a  mov     [rbp+var_18], 0
0x180043f62  lea     r13, WPP_GLOBAL_Control
0x180043f69  mov     rcx, cs:WPP_GLOBAL_Control
0x180043f70  cmp     rcx, r13
0x180043f73  jz      short loc_180043F96
0x180043f75  test    byte ptr [rcx+1Ch], 4
0x180043f79  jz      short loc_180043F96
0x180043f7b  cmp     byte ptr [rcx+19h], 4
0x180043f7f  jb      short loc_180043F96
0x180043f81  mov     edx, 5Dh ; ']'
0x180043f86  lea     r8, WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids
0x180043f8d  mov     rcx, [rcx+10h]
0x180043f91  call    WPP_SF_
0x180043f96  mov     rax, [rbx]
0x180043f99  lea     r8, [rbp+var_18]
0x180043f9d  lea     rdx, _GUID_27354132_7f64_5b0f_8f00_5d77afbe261e
0x180043fa4  mov     rcx, rbx
0x180043fa7  mov     rax, [rax]
0x180043faa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043faf  mov     ebx, eax
0x180043fb1  test    eax, eax
0x180043fb3  js      loc_18004414A
0x180043fb9  lea     r8, [rbp+arg_0]; unsigned __int8
0x180043fbd  mov     dl, 1; struct IDiscRecorder2Ex *
0x180043fbf  mov     rcx, [rbp+var_18]; this
0x180043fc3  call    ?GetCurrentDriveSpeed@Imapi2Utility@@YAJPEAUIDiscRecorder2Ex@@EPEAK@Z; Imapi2Utility::GetCurrentDriveSpeed(IDiscRecorder2Ex *,uchar,ulong *)
0x180043fc8  mov     ebx, eax
0x180043fca  test    eax, eax
0x180043fcc  js      loc_180044119
0x180043fd2  mov     edx, [rbp+arg_0]; enum _IMAPI_MEDIA_PHYSICAL_TYPE
0x180043fd5  mov     [rsi], edx
0x180043fd7  mov     r8, r14; unsigned int
0x180043fda  mov     ecx, edi; this
0x180043fdc  call    ?FuzzyConvert_KBps2SectorsPerSecond@Imapi2Utility@@YAJW4_IMAPI_MEDIA_PHYSICAL_TYPE@@KPEAK@Z; Imapi2Utility::FuzzyConvert_KBps2SectorsPerSecond(_IMAPI_MEDIA_PHYSICAL_TYPE,ulong,ulong *)
0x180043fe1  mov     ebx, eax
0x180043fe3  test    eax, eax
0x180043fe5  js      loc_180044119
0x180043feb  mov     [rbp+pv], 0
0x180043ff3  mov     [rbp+arg_0], 0
0x180043ffa  mov     rcx, [rbp+var_18]
0x180043ffe  mov     rax, [rcx]
0x180044001  lea     rdx, [rbp+arg_0]
0x180044005  mov     [rsp+48h+var_28], rdx
0x18004400a  lea     r9, [rbp+pv]
0x18004400e  xor     r8d, r8d
0x180044011  lea     edx, [r8+2Ah]
0x180044015  mov     rax, [rax+68h]
0x180044019  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004401e  mov     ebx, eax
0x180044020  mov     rdi, [rbp+arg_20]
0x180044024  test    eax, eax
0x180044026  js      loc_1800440CC
0x18004402c  mov     edx, [rbp+arg_0]; struct _CDVD_CAPABILITIES_PAGE *
0x18004402f  mov     rcx, [rbp+pv]; this
0x180044033  call    ?ValidateCapabilitiesModePageLength@Imapi2Utility@@YAJQEAU_CDVD_CAPABILITIES_PAGE@@K@Z; Imapi2Utility::ValidateCapabilitiesModePageLength(_CDVD_CAPABILITIES_PAGE * const,ulong)
0x180044038  mov     ebx, eax
0x18004403a  test    eax, eax
0x18004403c  js      loc_1800440CC
0x180044042  mov     rax, [rbp+pv]
0x180044046  cmp     byte ptr [rax+1], 1Ch
0x18004404a  jb      short loc_18004409A
0x18004404c  movzx   edx, byte ptr [rax+1Bh]
0x180044050  mov     al, dl
0x180044052  and     al, 3
0x180044054  jz      short loc_1800440C7
0x180044056  mov     ecx, 1
0x18004405b  cmp     al, cl
0x18004405d  jnz     short loc_180044064
0x18004405f  mov     [rdi], cx
0x180044062  jmp     short loc_1800440CC
0x180044064  mov     rcx, cs:WPP_GLOBAL_Control
0x18004406b  cmp     rcx, r13
0x18004406e  jz      short loc_1800440C7
0x180044070  test    byte ptr [rcx+1Ch], 4
0x180044074  jz      short loc_1800440C7
0x180044076  cmp     byte ptr [rcx+19h], 2
0x18004407a  jb      short loc_1800440C7
0x18004407c  mov     r9d, edx
0x18004407f  and     r9d, 3
0x180044083  mov     edx, 5Eh ; '^'
0x180044088  lea     r8, WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids
0x18004408f  mov     rcx, [rcx+10h]
0x180044093  call    WPP_SF_d
0x180044098  jmp     short loc_1800440C7
0x18004409a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800440a1  cmp     rcx, r13
0x1800440a4  jz      short loc_1800440C7
0x1800440a6  test    byte ptr [rcx+1Ch], 4
0x1800440aa  jz      short loc_1800440C7
0x1800440ac  cmp     byte ptr [rcx+19h], 3
0x1800440b0  jb      short loc_1800440C7
0x1800440b2  mov     edx, 5Fh ; '_'
0x1800440b7  lea     r8, WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids
0x1800440be  mov     rcx, [rcx+10h]
0x1800440c2  call    WPP_SF_
0x1800440c7  xor     eax, eax
0x1800440c9  mov     [rdi], ax
0x1800440cc  mov     rcx, [rbp+pv]; pv
0x1800440d0  call    cs:__imp_CoTaskMemFree
0x1800440d6  test    ebx, ebx
0x1800440d8  js      short loc_180044119
0x1800440da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800440e1  cmp     rcx, r13
0x1800440e4  jz      short loc_18004414A
0x1800440e6  test    byte ptr [rcx+1Ch], 4
0x1800440ea  jz      short loc_18004414A
0x1800440ec  cmp     byte ptr [rcx+19h], 4
0x1800440f0  jb      short loc_18004414A
0x1800440f2  movsx   eax, word ptr [rdi]
0x1800440f5  mov     edx, 60h ; '`'
0x1800440fa  mov     [rsp+48h+var_20], eax
0x1800440fe  mov     eax, [rsi]
0x180044100  mov     dword ptr [rsp+48h+var_28], eax
0x180044104  mov     r9d, [r14]
0x180044107  lea     r8, WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids
0x18004410e  mov     rcx, [rcx+10h]
0x180044112  call    WPP_SF_ddD
0x180044117  jmp     short loc_18004414A
0x180044119  mov     rcx, cs:WPP_GLOBAL_Control
0x180044120  cmp     rcx, r13
0x180044123  jz      short loc_18004414A
0x180044125  test    byte ptr [rcx+1Ch], 4
0x180044129  jz      short loc_18004414A
0x18004412b  cmp     byte ptr [rcx+19h], 4
0x18004412f  jb      short loc_18004414A
0x180044131  mov     edx, 61h ; 'a'
0x180044136  mov     r9d, ebx
0x180044139  lea     r8, WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids
0x180044140  mov     rcx, [rcx+10h]
0x180044144  call    WPP_SF_d
0x180044149  nop
0x18004414a  lea     rcx, [rbp+var_18]
0x18004414e  call    ??1?$CComPtrBase@UIDiscRecorder2Ex@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IDiscRecorder2Ex>::~CComPtrBase<IDiscRecorder2Ex>(void)
0x180044153  mov     eax, ebx
0x180044155  add     rsp, 48h
0x180044159  pop     r14
0x18004415b  pop     r13
0x18004415d  pop     rdi
0x18004415e  pop     rsi
0x18004415f  pop     rbx
0x180044160  pop     rbp
0x180044161  retn
```
