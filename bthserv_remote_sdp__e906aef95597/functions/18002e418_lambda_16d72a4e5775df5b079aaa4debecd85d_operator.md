# _lambda_16d72a4e5775df5b079aaa4debecd85d_::operator()

- ea: `0x18002e418`
- end: `0x18002e774`
- name: `_lambda_16d72a4e5775df5b079aaa4debecd85d_::operator()`
- size: `860`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18002dcb0`

## callees

- `0x1800017a0`
- `0x180003740`
- `0x180011b9c`
- `0x1800120b8`
- `0x180012384`
- `0x18002c9b8`
- `0x18002dd98`
- `0x18002e418`
- `0x18002f4ec`
- `0x18002fc64`
- `0x180031720`

## string_xrefs

- `0x18002e6f4`: `onecore\drivers\wdm\bluetooth\libs\bthleprepairing\bthleprepairingdevice.cpp`
- `0x18002e75f`: `onecore\drivers\wdm\bluetooth\libs\bthleprepairing\bthleprepairingdevice.cpp`

## pseudocode

```c
void __fastcall lambda_16d72a4e5775df5b079aaa4debecd85d_::operator()(ULONGLONG *a1, __int64 a2, __int64 a3)
{
  ULONGLONG v3; // rdi
  _BYTE *v5; // rcx
  char v6; // bl
  _UNKNOWN **v7; // r9
  int v8; // eax
  int v9; // r8d
  int v10; // edx
  bool v11; // cf
  int *v12; // rsi
  int v13; // eax
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // r8
  __int64 v17; // r9
  unsigned int v18; // eax
  unsigned int v19; // eax
  int v20; // [rsp+20h] [rbp-98h]
  int v21; // [rsp+60h] [rbp-58h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v22; // [rsp+68h] [rbp-50h] BYREF
  ULONGLONG v23; // [rsp+78h] [rbp-40h]
  int v24; // [rsp+80h] [rbp-38h]
  int v25; // [rsp+84h] [rbp-34h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  v3 = *a1;
  v5 = WPP_GLOBAL_Control;
  v6 = 1;
  LOBYTE(a2) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u;
  v7 = (_UNKNOWN **)WPP_RECORDER_INITIALIZED;
  if ( (_BYTE)a2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_si(*((_QWORD *)WPP_GLOBAL_Control + 2), a2, a3, *((_QWORD *)WPP_GLOBAL_Control + 5));
    v5 = WPP_GLOBAL_Control;
    v7 = (_UNKNOWN **)WPP_RECORDER_INITIALIZED;
  }
  dword_1800463E6 = *(_DWORD *)(v3 + 48);
  word_1800463EA = WORD2(*(_QWORD *)(v3 + 48));
  xmmword_1800463EE = *(_OWORD *)(v3 + 25);
  qword_180046406 = *(_QWORD *)(v3 + 17);
  LOBYTE(a2) = v5 != (_BYTE *)&WPP_GLOBAL_Control && v5[25] >= 5u;
  if ( (_BYTE)a2 || v7 != &WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(a3) = v7 != &WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_si(*((_QWORD *)v5 + 2), a2, a3, *((_QWORD *)v5 + 5));
    v5 = WPP_GLOBAL_Control;
    v7 = (_UNKNOWN **)WPP_RECORDER_INITIALIZED;
  }
  LOBYTE(a2) = v5 != (_BYTE *)&WPP_GLOBAL_Control && v5[25] >= 5u;
  LOBYTE(a3) = v7 != &WPP_RECORDER_INITIALIZED;
  if ( (_BYTE)a2 || v7 != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_si(*((_QWORD *)v5 + 2), a2, a3, *((_QWORD *)v5 + 5));
  v22.Ptr = v3;
  *(_QWORD *)&v22.Size = &v21;
  v8 = wil::ResultFromException__lambda_cb293c6ec7bc4deeec064c1f58322c0f___(&v22, a2, a3);
  v10 = 0;
  v21 = v8;
  if ( v8 )
    v11 = *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u;
  else
    v11 = *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u;
  LOBYTE(v10) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (LOBYTE(v10) = !v11, v10);
  if ( (_BYTE)v10 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v9) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_sqd(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, v9, *((_QWORD *)WPP_GLOBAL_Control + 5));
    v8 = v21;
  }
  v12 = (int *)a1[1];
  *v12 = v8;
  if ( v21 < 0 )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      v6 = 0;
    if ( v6 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v10) = v6;
      LOBYTE(v9) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sD(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, v9, *((_QWORD *)WPP_GLOBAL_Control + 5));
    }
    v18 = wil::verify_hresult<long>((unsigned int)*v12);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1EF,
      (unsigned int)"onecore\\drivers\\wdm\\bluetooth\\libs\\bthleprepairing\\bthleprepairingdevice.cpp",
      (const char *)v18,
      v20);
  }
  v13 = Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice::FinishOobPairing((Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice *)v3);
  *v12 = v13;
  if ( v13 < 0 )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      v6 = 0;
    if ( v6 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v14) = v6;
      LOBYTE(v16) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sD(*((_QWORD *)WPP_GLOBAL_Control + 2), v14, v16, *((_QWORD *)WPP_GLOBAL_Control + 5));
    }
    v19 = wil::verify_hresult<long>((unsigned int)*v12);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1F6,
      (unsigned int)"onecore\\drivers\\wdm\\bluetooth\\libs\\bthleprepairing\\bthleprepairingdevice.cpp",
      (const char *)v19,
      v20);
  }
  if ( (Microsoft_Windows_Bluetooth_BthLEPrepairingEnableBits & 1) != 0 )
  {
    v25 = 0;
    v23 = v3 + 17;
    v24 = 8;
    McGenEventWrite_EventWriteTransfer(v15, v14, v16, v17, &v22);
  }
  Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice::CleanupPreviousAssociations((Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice *)v3);
}

```

## disassembly

```asm
0x18002e418  mov     [rsp+arg_8], rbx
0x18002e41d  mov     [rsp+arg_10], rbp
0x18002e422  mov     [rsp+arg_18], rsi
0x18002e427  push    rdi
0x18002e428  push    r12
0x18002e42a  push    r13
0x18002e42c  push    r14
0x18002e42e  push    r15
0x18002e430  sub     rsp, 90h
0x18002e437  mov     rax, cs:__security_cookie
0x18002e43e  xor     rax, rsp
0x18002e441  mov     [rsp+0B8h+var_30], rax
0x18002e449  mov     rdi, [rcx]
0x18002e44c  mov     rsi, rcx
0x18002e44f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e456  lea     rbp, WPP_GLOBAL_Control
0x18002e45d  mov     bl, 1
0x18002e45f  mov     r15b, 5
0x18002e462  cmp     rcx, rbp
0x18002e465  jz      short loc_18002E471
0x18002e467  cmp     [rcx+19h], r15b
0x18002e46b  jb      short loc_18002E471
0x18002e46d  mov     dl, bl
0x18002e46f  jmp     short loc_18002E473
0x18002e471  xor     dl, dl
0x18002e473  mov     r9, cs:WPP_RECORDER_INITIALIZED
0x18002e47a  lea     r13, WPP_RECORDER_INITIALIZED
0x18002e481  cmp     r9, r13
0x18002e484  lea     r12, WPP_95fda3e624973c89daad3dc985e66758_Traceguids
0x18002e48b  setnz   r8b
0x18002e48f  test    dl, dl
0x18002e491  jnz     short loc_18002E498
0x18002e493  test    r8b, r8b
0x18002e496  jz      short loc_18002E4C4
0x18002e498  mov     r9, [rcx+28h]
0x18002e49c  mov     rcx, [rcx+10h]
0x18002e4a0  mov     [rsp+0B8h+var_70], rdi
0x18002e4a5  mov     [rsp+0B8h+var_80], r12
0x18002e4aa  mov     [rsp+0B8h+var_88], 33h ; '3'
0x18002e4b1  call    WPP_RECORDER_AND_TRACE_SF_si
0x18002e4b6  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e4bd  mov     r9, cs:WPP_RECORDER_INITIALIZED
0x18002e4c4  mov     eax, [rdi+30h]
0x18002e4c7  lea     r14, [rdi+11h]
0x18002e4cb  mov     cs:dword_1800463E6, eax
0x18002e4d1  mov     rax, [rdi+30h]
0x18002e4d5  shr     rax, 20h
0x18002e4d9  mov     cs:word_1800463EA, ax
0x18002e4e0  movups  xmm0, xmmword ptr [rdi+19h]
0x18002e4e4  movdqu  cs:xmmword_1800463EE, xmm0
0x18002e4ec  mov     rax, [r14]
0x18002e4ef  mov     cs:qword_180046406, rax
0x18002e4f6  cmp     rcx, rbp
0x18002e4f9  jz      short loc_18002E505
0x18002e4fb  cmp     [rcx+19h], r15b
0x18002e4ff  jb      short loc_18002E505
0x18002e501  mov     dl, bl
0x18002e503  jmp     short loc_18002E507
0x18002e505  xor     dl, dl
0x18002e507  cmp     r9, r13
0x18002e50a  setnz   r8b
0x18002e50e  test    dl, dl
0x18002e510  jnz     short loc_18002E517
0x18002e512  test    r8b, r8b
0x18002e515  jz      short loc_18002E543
0x18002e517  mov     r9, [rcx+28h]
0x18002e51b  mov     rcx, [rcx+10h]
0x18002e51f  mov     [rsp+0B8h+var_70], rdi
0x18002e524  mov     [rsp+0B8h+var_80], r12
0x18002e529  mov     [rsp+0B8h+var_88], 34h ; '4'
0x18002e530  call    WPP_RECORDER_AND_TRACE_SF_si
0x18002e535  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e53c  mov     r9, cs:WPP_RECORDER_INITIALIZED
0x18002e543  cmp     rcx, rbp
0x18002e546  jz      short loc_18002E552
0x18002e548  cmp     [rcx+19h], r15b
0x18002e54c  jb      short loc_18002E552
0x18002e54e  mov     dl, bl
0x18002e550  jmp     short loc_18002E554
0x18002e552  xor     dl, dl
0x18002e554  cmp     r9, r13
0x18002e557  setnz   r8b
0x18002e55b  test    dl, dl
0x18002e55d  jnz     short loc_18002E564
0x18002e55f  test    r8b, r8b
0x18002e562  jz      short loc_18002E582
0x18002e564  mov     r9, [rcx+28h]
0x18002e568  mov     rcx, [rcx+10h]
0x18002e56c  mov     [rsp+0B8h+var_70], rdi
0x18002e571  mov     [rsp+0B8h+var_80], r12
0x18002e576  mov     [rsp+0B8h+var_88], 35h ; '5'
0x18002e57d  call    WPP_RECORDER_AND_TRACE_SF_si
0x18002e582  lea     rax, [rsp+0B8h+var_58]
0x18002e587  mov     [rsp+0B8h+var_50.Ptr], rdi
0x18002e58c  lea     rcx, [rsp+0B8h+var_50]
0x18002e591  mov     qword ptr [rsp+0B8h+var_50.Size], rax
0x18002e596  call    wil__ResultFromException__lambda_cb293c6ec7bc4deeec064c1f58322c0f___
0x18002e59b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e5a2  xor     edx, edx
0x18002e5a4  mov     [rsp+0B8h+var_58], eax
0x18002e5a8  mov     r12b, 2
0x18002e5ab  test    eax, eax
0x18002e5ad  jnz     short loc_18002E5B5
0x18002e5af  cmp     [rcx+19h], r15b
0x18002e5b3  jmp     short loc_18002E5B9
0x18002e5b5  cmp     [rcx+19h], r12b
0x18002e5b9  setnb   dl
0x18002e5bc  cmp     rcx, rbp
0x18002e5bf  jz      short loc_18002E5C9
0x18002e5c1  test    edx, edx
0x18002e5c3  jz      short loc_18002E5C9
0x18002e5c5  mov     dl, bl
0x18002e5c7  jmp     short loc_18002E5CB
0x18002e5c9  xor     dl, dl
0x18002e5cb  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18002e5d2  setnz   r8b
0x18002e5d6  test    dl, dl
0x18002e5d8  jnz     short loc_18002E5DF
0x18002e5da  test    r8b, r8b
0x18002e5dd  jz      short loc_18002E60E
0x18002e5df  mov     r9, [rcx+28h]
0x18002e5e3  lea     r15, WPP_95fda3e624973c89daad3dc985e66758_Traceguids
0x18002e5ea  mov     rcx, [rcx+10h]
0x18002e5ee  mov     [rsp+0B8h+var_68], eax
0x18002e5f2  mov     [rsp+0B8h+var_70], rdi
0x18002e5f7  mov     [rsp+0B8h+var_80], r15
0x18002e5fc  mov     [rsp+0B8h+var_88], 38h ; '8'
0x18002e603  call    WPP_RECORDER_AND_TRACE_SF_sqd
0x18002e608  mov     eax, [rsp+0B8h+var_58]
0x18002e60c  jmp     short loc_18002E615
0x18002e60e  lea     r15, WPP_95fda3e624973c89daad3dc985e66758_Traceguids
0x18002e615  mov     rsi, [rsi+8]
0x18002e619  mov     [rsi], eax
0x18002e61b  mov     eax, [rsp+0B8h+var_58]
0x18002e61f  test    eax, eax
0x18002e621  js      short loc_18002E69E
0x18002e623  mov     rcx, rdi; this
0x18002e626  call    ?FinishOobPairing@BthLEPrepairingDevice@BthLEPrepairing@Bluetooth@Internal@Windows@@AEAAJXZ; Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice::FinishOobPairing(void)
0x18002e62b  mov     [rsi], eax
0x18002e62d  test    eax, eax
0x18002e62f  js      loc_18002E709
0x18002e635  test    cs:Microsoft_Windows_Bluetooth_BthLEPrepairingEnableBits, bl
0x18002e63b  jz      short loc_18002E664
0x18002e63d  and     [rsp+0B8h+var_34], 0
0x18002e645  lea     rax, [rsp+0B8h+var_50]
0x18002e64a  mov     qword ptr [rsp+0B8h+var_98], rax; PEVENT_DATA_DESCRIPTOR
0x18002e64f  mov     [rsp+0B8h+var_40], r14
0x18002e654  mov     [rsp+0B8h+var_38], 8
0x18002e65f  call    McGenEventWrite_EventWriteTransfer
0x18002e664  mov     rcx, rdi; this
0x18002e667  call    ?CleanupPreviousAssociations@BthLEPrepairingDevice@BthLEPrepairing@Bluetooth@Internal@Windows@@AEAAXXZ; Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice::CleanupPreviousAssociations(void)
0x18002e66c  mov     rcx, [rsp+0B8h+var_30]
0x18002e674  xor     rcx, rsp; StackCookie
0x18002e677  call    __security_check_cookie
0x18002e67c  lea     r11, [rsp+0B8h+var_28]
0x18002e684  mov     rbx, [r11+38h]
0x18002e688  mov     rbp, [r11+40h]
0x18002e68c  mov     rsi, [r11+48h]
0x18002e690  mov     rsp, r11
0x18002e693  pop     r15
0x18002e695  pop     r14
0x18002e697  pop     r13
0x18002e699  pop     r12
0x18002e69b  pop     rdi
0x18002e69c  retn
0x18002e69e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e6a5  cmp     rcx, rbp
0x18002e6a8  jz      short loc_18002E6B0
0x18002e6aa  cmp     [rcx+19h], r12b
0x18002e6ae  jnb     short loc_18002E6B2
0x18002e6b0  xor     bl, bl
0x18002e6b2  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18002e6b9  setnz   r8b
0x18002e6bd  test    bl, bl
0x18002e6bf  jnz     short loc_18002E6C6
0x18002e6c1  test    r8b, r8b
0x18002e6c4  jz      short loc_18002E6E5
0x18002e6c6  mov     r9, [rcx+28h]
0x18002e6ca  mov     dl, bl
0x18002e6cc  mov     rcx, [rcx+10h]
0x18002e6d0  mov     dword ptr [rsp+0B8h+var_70], eax
0x18002e6d4  mov     [rsp+0B8h+var_80], r15
0x18002e6d9  mov     [rsp+0B8h+var_88], 30h ; '0'
0x18002e6e0  call    WPP_RECORDER_AND_TRACE_SF_sD
0x18002e6e5  mov     ecx, [rsi]
0x18002e6e7  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18002e6ec  mov     rcx, [rsp+0B8h]; this
0x18002e6f4  lea     r8, aOnecoreDrivers_6; "onecore\\drivers\\wdm\\bluetooth\\libs"...
0x18002e6fb  mov     r9d, eax; char *
0x18002e6fe  mov     edx, 1EFh; void *
0x18002e703  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002e709  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e710  cmp     rcx, rbp
0x18002e713  jz      short loc_18002E71B
0x18002e715  cmp     [rcx+19h], r12b
0x18002e719  jnb     short loc_18002E71D
0x18002e71b  xor     bl, bl
0x18002e71d  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18002e724  setnz   r8b
0x18002e728  test    bl, bl
0x18002e72a  jnz     short loc_18002E731
0x18002e72c  test    r8b, r8b
0x18002e72f  jz      short loc_18002E750
0x18002e731  mov     r9, [rcx+28h]
0x18002e735  mov     dl, bl
0x18002e737  mov     rcx, [rcx+10h]
0x18002e73b  mov     dword ptr [rsp+0B8h+var_70], eax
0x18002e73f  mov     [rsp+0B8h+var_80], r15
0x18002e744  mov     [rsp+0B8h+var_88], 31h ; '1'
0x18002e74b  call    WPP_RECORDER_AND_TRACE_SF_sD
0x18002e750  mov     ecx, [rsi]
0x18002e752  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18002e757  mov     rcx, [rsp+0B8h]; this
0x18002e75f  lea     r8, aOnecoreDrivers_6; "onecore\\drivers\\wdm\\bluetooth\\libs"...
0x18002e766  mov     r9d, eax; char *
0x18002e769  mov     edx, 1F6h; void *
0x18002e76e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
