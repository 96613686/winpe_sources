# Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice::Stop(void)

- ea: `0x180030c38`
- end: `0x180030f75`
- name: `?Stop@BthLEPrepairingDevice@BthLEPrepairing@Bluetooth@Internal@Windows@@QEAAJXZ`
- size: `829`
- prototype: `__int64 __fastcall(Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice *__hidden this)`
- caller_count: `4`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x18002c060`
- `0x18002cfcc`
- `0x18002e1d8`
- `0x180030650`

## callees

- `0x180012384`
- `0x18002c9b8`
- `0x180030c38`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180030e66`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180030e66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030e7e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030e7e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180030e9d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180030e9d`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x180030db8`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x180030db8`
- `deviceassociation!DafCloseAssociationContext` at `0x180030e8f`
- `deviceassociation!DafCloseAssociationContext` at `0x180030e8f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice::Stop(__int64 **this)
{
  char v2; // si
  bool v3; // dl
  _BYTE *v4; // rcx
  bool v5; // dl
  bool v6; // dl
  __int64 v7; // rbx
  bool v8; // dl
  bool v9; // dl
  __int64 *v10; // rcx
  __int64 *v11; // rbp
  DWORD LastError; // ebx
  __int64 v13; // rdx
  __int64 v14; // r8
  _BYTE *v15; // rcx
  bool v16; // dl
  _UNKNOWN **v17; // rax

  v2 = 1;
  v3 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u;
  if ( v3 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_si(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v3,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
  _InterlockedExchange((volatile __int32 *)this + 35, 1);
  v4 = WPP_GLOBAL_Control;
  v5 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u;
  if ( v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_AND_TRACE_SF_si(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v5,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
    v4 = WPP_GLOBAL_Control;
  }
  if ( *this && (unsigned __int64)(**this - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    if ( *((_DWORD *)this + 34) == 997 )
    {
      v6 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u;
      v7 = -1;
      if ( v6 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_AND_TRACE_SF_si(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v6,
          WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
          *((_QWORD *)WPP_GLOBAL_Control + 5));
      if ( *this )
        v7 = **this;
      CancelIoEx((HANDLE)v7, (LPOVERLAPPED)(this + 11));
    }
    v4 = WPP_GLOBAL_Control;
  }
  v8 = v4 != (_BYTE *)&WPP_GLOBAL_Control && v4[25] >= 5u;
  if ( v8 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_AND_TRACE_SF_si(
      *((_QWORD *)v4 + 2),
      v8,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)v4 + 5));
    v4 = WPP_GLOBAL_Control;
  }
  v9 = v4 != (_BYTE *)&WPP_GLOBAL_Control && v4[25] >= 5u;
  if ( v9 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_si(
      *((_QWORD *)v4 + 2),
      v9,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)v4 + 5));
  v10 = this[257];
  if ( v10 )
    SetEvent(v10);
  v11 = this[255];
  if ( v11 )
  {
    LastError = GetLastError();
    DafCloseAssociationContext(v11, v13, v14);
    SetLastError(LastError);
  }
  this[255] = 0;
  v15 = WPP_GLOBAL_Control;
  v16 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u;
  v17 = (_UNKNOWN **)WPP_RECORDER_INITIALIZED;
  if ( v16 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_AND_TRACE_SF_si(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v16,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
    v15 = WPP_GLOBAL_Control;
    v17 = (_UNKNOWN **)WPP_RECORDER_INITIALIZED;
  }
  if ( v15 == (_BYTE *)&WPP_GLOBAL_Control || v15[25] < 5u )
    v2 = 0;
  if ( v2 || v17 != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_sqd(*((_QWORD *)v15 + 2), v2, v17 != &WPP_RECORDER_INITIALIZED, *((_QWORD *)v15 + 5));
  return 0;
}

```

## disassembly

```asm
0x180030c38  mov     rax, rsp
0x180030c3b  mov     [rax+8], rbx
0x180030c3f  mov     [rax+10h], rbp
0x180030c43  mov     [rax+18h], rsi
0x180030c47  mov     [rax+20h], rdi
0x180030c4b  push    r12
0x180030c4d  push    r13
0x180030c4f  push    r14
0x180030c51  sub     rsp, 60h
0x180030c55  mov     rdi, rcx
0x180030c58  lea     r14, WPP_GLOBAL_Control
0x180030c5f  mov     esi, 1
0x180030c64  mov     rcx, cs:WPP_GLOBAL_Control
0x180030c6b  cmp     rcx, r14
0x180030c6e  jz      short loc_180030C7B
0x180030c70  cmp     byte ptr [rcx+19h], 5
0x180030c74  jb      short loc_180030C7B
0x180030c76  mov     dl, sil
0x180030c79  jmp     short loc_180030C7D
0x180030c7b  xor     dl, dl
0x180030c7d  lea     r12, WPP_RECORDER_INITIALIZED
0x180030c84  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x180030c8b  setnz   r8b
0x180030c8f  lea     r13, WPP_95fda3e624973c89daad3dc985e66758_Traceguids
0x180030c96  test    dl, dl
0x180030c98  jnz     short loc_180030C9F
0x180030c9a  test    r8b, r8b
0x180030c9d  jz      short loc_180030CBD
0x180030c9f  mov     [rsp+78h+var_30], rdi
0x180030ca4  mov     [rsp+78h+var_40], r13
0x180030ca9  mov     [rsp+78h+var_48], 22h ; '"'
0x180030cb0  mov     r9, [rcx+28h]
0x180030cb4  mov     rcx, [rcx+10h]
0x180030cb8  call    WPP_RECORDER_AND_TRACE_SF_si
0x180030cbd  mov     eax, esi
0x180030cbf  xchg    eax, [rdi+8Ch]
0x180030cc5  mov     rcx, cs:WPP_GLOBAL_Control
0x180030ccc  cmp     rcx, r14
0x180030ccf  jz      short loc_180030CDC
0x180030cd1  cmp     byte ptr [rcx+19h], 5
0x180030cd5  jb      short loc_180030CDC
0x180030cd7  mov     dl, sil
0x180030cda  jmp     short loc_180030CDE
0x180030cdc  xor     dl, dl
0x180030cde  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x180030ce5  setnz   r8b
0x180030ce9  test    dl, dl
0x180030ceb  jnz     short loc_180030CF2
0x180030ced  test    r8b, r8b
0x180030cf0  jz      short loc_180030D17
0x180030cf2  mov     [rsp+78h+var_30], rdi
0x180030cf7  mov     [rsp+78h+var_40], r13
0x180030cfc  mov     [rsp+78h+var_48], 24h ; '$'
0x180030d03  mov     r9, [rcx+28h]
0x180030d07  mov     rcx, [rcx+10h]
0x180030d0b  call    WPP_RECORDER_AND_TRACE_SF_si
0x180030d10  mov     rcx, cs:WPP_GLOBAL_Control
0x180030d17  mov     rax, [rdi]
0x180030d1a  test    rax, rax
0x180030d1d  jz      loc_180030DCB
0x180030d23  mov     rax, [rax]
0x180030d26  dec     rax
0x180030d29  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180030d2d  ja      loc_180030DCB
0x180030d33  mov     eax, [rdi+88h]
0x180030d39  cmp     eax, 3E5h
0x180030d3e  jnz     loc_180030DC4
0x180030d44  mov     rcx, cs:WPP_GLOBAL_Control
0x180030d4b  cmp     rcx, r14
0x180030d4e  jz      short loc_180030D5B
0x180030d50  cmp     byte ptr [rcx+19h], 3
0x180030d54  jb      short loc_180030D5B
0x180030d56  mov     dl, sil
0x180030d59  jmp     short loc_180030D5D
0x180030d5b  xor     dl, dl
0x180030d5d  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x180030d64  setnz   r10b
0x180030d68  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180030d6c  test    dl, dl
0x180030d6e  jnz     short loc_180030D75
0x180030d70  test    r10b, r10b
0x180030d73  jz      short loc_180030DA6
0x180030d75  mov     rax, [rdi]
0x180030d78  test    rax, rax
0x180030d7b  jz      short loc_180030D82
0x180030d7d  mov     r8, [rax]
0x180030d80  jmp     short loc_180030D85
0x180030d82  mov     r8, rbx
0x180030d85  mov     [rsp+78h+var_30], r8
0x180030d8a  mov     [rsp+78h+var_40], r13
0x180030d8f  mov     [rsp+78h+var_48], 25h ; '%'
0x180030d96  mov     r9, [rcx+28h]
0x180030d9a  mov     r8b, r10b
0x180030d9d  mov     rcx, [rcx+10h]
0x180030da1  call    WPP_RECORDER_AND_TRACE_SF_si
0x180030da6  mov     rax, [rdi]
0x180030da9  test    rax, rax
0x180030dac  jz      short loc_180030DB1
0x180030dae  mov     rbx, [rax]
0x180030db1  lea     rdx, [rdi+58h]; lpOverlapped
0x180030db5  mov     rcx, rbx; hFile
0x180030db8  call    cs:__imp_CancelIoEx
0x180030dbf  nop     dword ptr [rax+rax+00h]
0x180030dc4  mov     rcx, cs:WPP_GLOBAL_Control
0x180030dcb  cmp     rcx, r14
0x180030dce  jz      short loc_180030DDB
0x180030dd0  cmp     byte ptr [rcx+19h], 5
0x180030dd4  jb      short loc_180030DDB
0x180030dd6  mov     dl, sil
0x180030dd9  jmp     short loc_180030DDD
0x180030ddb  xor     dl, dl
0x180030ddd  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x180030de4  setnz   r8b
0x180030de8  test    dl, dl
0x180030dea  jnz     short loc_180030DF1
0x180030dec  test    r8b, r8b
0x180030def  jz      short loc_180030E16
0x180030df1  mov     [rsp+78h+var_30], rdi
0x180030df6  mov     [rsp+78h+var_40], r13
0x180030dfb  mov     [rsp+78h+var_48], 26h ; '&'
0x180030e02  mov     r9, [rcx+28h]
0x180030e06  mov     rcx, [rcx+10h]
0x180030e0a  call    WPP_RECORDER_AND_TRACE_SF_si
0x180030e0f  mov     rcx, cs:WPP_GLOBAL_Control
0x180030e16  cmp     rcx, r14
0x180030e19  jz      short loc_180030E26
0x180030e1b  cmp     byte ptr [rcx+19h], 5
0x180030e1f  jb      short loc_180030E26
0x180030e21  mov     dl, sil
0x180030e24  jmp     short loc_180030E28
0x180030e26  xor     dl, dl
0x180030e28  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x180030e2f  setnz   r8b
0x180030e33  test    dl, dl
0x180030e35  jnz     short loc_180030E3C
0x180030e37  test    r8b, r8b
0x180030e3a  jz      short loc_180030E5A
0x180030e3c  mov     [rsp+78h+var_30], rdi
0x180030e41  mov     [rsp+78h+var_40], r13
0x180030e46  mov     [rsp+78h+var_48], 27h ; '''
0x180030e4d  mov     r9, [rcx+28h]
0x180030e51  mov     rcx, [rcx+10h]
0x180030e55  call    WPP_RECORDER_AND_TRACE_SF_si
0x180030e5a  mov     rcx, [rdi+808h]; hEvent
0x180030e61  test    rcx, rcx
0x180030e64  jz      short loc_180030E72
0x180030e66  call    cs:__imp_SetEvent
0x180030e6d  nop     dword ptr [rax+rax+00h]
0x180030e72  mov     rbp, [rdi+7F8h]
0x180030e79  test    rbp, rbp
0x180030e7c  jz      short loc_180030EAA
0x180030e7e  call    cs:__imp_GetLastError
0x180030e85  nop     dword ptr [rax+rax+00h]
0x180030e8a  mov     ebx, eax
0x180030e8c  mov     rcx, rbp
0x180030e8f  call    cs:__imp_DafCloseAssociationContext
0x180030e96  nop     dword ptr [rax+rax+00h]
0x180030e9b  mov     ecx, ebx; dwErrCode
0x180030e9d  call    cs:__imp_SetLastError
0x180030ea4  nop     dword ptr [rax+rax+00h]
0x180030ea9  nop
0x180030eaa  and     qword ptr [rdi+7F8h], 0
0x180030eb2  mov     rcx, cs:WPP_GLOBAL_Control
0x180030eb9  cmp     rcx, r14
0x180030ebc  jz      short loc_180030EC9
0x180030ebe  cmp     byte ptr [rcx+19h], 5
0x180030ec2  jb      short loc_180030EC9
0x180030ec4  mov     dl, sil
0x180030ec7  jmp     short loc_180030ECB
0x180030ec9  xor     dl, dl
0x180030ecb  mov     rax, cs:WPP_RECORDER_INITIALIZED
0x180030ed2  cmp     rax, r12
0x180030ed5  setnz   r8b
0x180030ed9  test    dl, dl
0x180030edb  jnz     short loc_180030EE2
0x180030edd  test    r8b, r8b
0x180030ee0  jz      short loc_180030F0E
0x180030ee2  mov     [rsp+78h+var_30], rdi
0x180030ee7  mov     [rsp+78h+var_40], r13
0x180030eec  mov     [rsp+78h+var_48], 28h ; '('
0x180030ef3  mov     r9, [rcx+28h]
0x180030ef7  mov     rcx, [rcx+10h]
0x180030efb  call    WPP_RECORDER_AND_TRACE_SF_si
0x180030f00  mov     rcx, cs:WPP_GLOBAL_Control
0x180030f07  mov     rax, cs:WPP_RECORDER_INITIALIZED
0x180030f0e  cmp     rcx, r14
0x180030f11  jz      short loc_180030F19
0x180030f13  cmp     byte ptr [rcx+19h], 5
0x180030f17  jnb     short loc_180030F1C
0x180030f19  xor     sil, sil
0x180030f1c  cmp     rax, r12
0x180030f1f  setnz   r8b
0x180030f23  test    sil, sil
0x180030f26  jnz     short loc_180030F2D
0x180030f28  test    r8b, r8b
0x180030f2b  jz      short loc_180030F53
0x180030f2d  and     [rsp+78h+var_28], 0
0x180030f32  mov     [rsp+78h+var_30], rdi
0x180030f37  mov     [rsp+78h+var_40], r13
0x180030f3c  mov     [rsp+78h+var_48], 23h ; '#'
0x180030f43  mov     r9, [rcx+28h]
0x180030f47  mov     dl, sil
0x180030f4a  mov     rcx, [rcx+10h]
0x180030f4e  call    WPP_RECORDER_AND_TRACE_SF_sqd
0x180030f53  xor     eax, eax
0x180030f55  lea     r11, [rsp+78h+var_18]
0x180030f5a  mov     rbx, [r11+20h]
0x180030f5e  mov     rbp, [r11+28h]
0x180030f62  mov     rsi, [r11+30h]
0x180030f66  mov     rdi, [r11+38h]
0x180030f6a  mov     rsp, r11
0x180030f6d  pop     r14
0x180030f6f  pop     r13
0x180030f71  pop     r12
0x180030f73  retn
```
