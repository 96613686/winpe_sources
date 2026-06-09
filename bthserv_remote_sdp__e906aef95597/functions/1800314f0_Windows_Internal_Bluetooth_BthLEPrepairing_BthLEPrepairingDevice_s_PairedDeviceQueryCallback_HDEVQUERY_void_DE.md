# Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice::s_PairedDeviceQueryCallback(HDEVQUERY__ *,void *,_DEV_QUERY_RESULT_ACTION_DATA const *)

- ea: `0x1800314f0`
- end: `0x1800316f0`
- name: `?s_PairedDeviceQueryCallback@BthLEPrepairingDevice@BthLEPrepairing@Bluetooth@Internal@Windows@@CAXPEAUHDEVQUERY__@@PEAXPEBU_DEV_QUERY_RESULT_ACTION_DATA@@@Z`
- size: `512`
- prototype: `void __fastcall(struct HDEVQUERY__ *, void *, const struct _DEV_QUERY_RESULT_ACTION_DATA *)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x1800017a0`
- `0x18001245c`
- `0x180014e30`
- `0x180014f14`
- `0x18002de94`
- `0x1800314f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800316b6`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800316b6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice::s_PairedDeviceQueryCallback(
        struct HDEVQUERY__ *a1,
        HANDLE *a2,
        const struct _DEV_QUERY_RESULT_ACTION_DATA *a3)
{
  const struct _DEV_QUERY_RESULT_ACTION_DATA *v3; // rbx
  HANDLE *v4; // rsi
  _BYTE *v5; // r10
  char v6; // di
  _UNKNOWN **v7; // r9
  __int64 v8; // rdx
  int v9; // r8d
  __int64 v10; // rax
  __int64 v11; // rcx
  HANDLE v12; // rdx
  __int64 v13; // r8
  bool v14; // dl
  int v15; // [rsp+20h] [rbp-98h]
  int v16; // [rsp+28h] [rbp-90h]
  _BYTE v17[16]; // [rsp+50h] [rbp-68h] BYREF
  _BYTE v18[32]; // [rsp+60h] [rbp-58h] BYREF

  v3 = a3;
  v4 = a2;
  if ( *(_DWORD *)a3 )
  {
    if ( *(_DWORD *)a3 == 1 )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
      {
        LOBYTE(a2) = 0;
        v6 = 1;
      }
      else
      {
        v6 = 1;
        LOBYTE(a2) = 1;
      }
      v7 = (_UNKNOWN **)WPP_RECORDER_INITIALIZED;
      if ( (_BYTE)a2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          (_DWORD)a2,
          (_DWORD)a3,
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          v15,
          v16,
          41,
          (__int64)WPP_95fda3e624973c89daad3dc985e66758_Traceguids);
        v5 = WPP_GLOBAL_Control;
        v7 = (_UNKNOWN **)WPP_RECORDER_INITIALIZED;
      }
      v8 = 0;
      v9 = 7;
      while ( (unsigned int)v8 < *((_DWORD *)v3 + 6) )
      {
        v10 = 6 * v8;
        v11 = *((_QWORD *)v3 + 4);
        if ( DEVPKEY_BluetoothLE_PrepairingDeviceId == *(_OWORD *)(v11 + 48 * v8)
          && *(_DWORD *)(v11 + 48 * v8 + 16) == 7
          && *(_DWORD *)(v11 + 48 * v8 + 32) == 4099
          && *(_DWORD *)(v11 + 48 * v8 + 36) == 8 )
        {
          v12 = *v4;
          if ( **(_QWORD **)(v11 + 8 * v10 + 40) == *(_QWORD *)((char *)*v4 + 17) )
          {
            if ( v5 == (_BYTE *)&WPP_GLOBAL_Control || v5[25] < 4u )
              v6 = 0;
            if ( v6 || v7 != &WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v12) = v6;
              LOBYTE(v9) = v7 != &WPP_RECORDER_INITIALIZED;
              WPP_RECORDER_AND_TRACE_SF_sS(
                *((_QWORD *)v5 + 2),
                (_DWORD)v12,
                v9,
                *((_QWORD *)v5 + 5),
                v15,
                v16,
                42,
                (__int64)WPP_95fda3e624973c89daad3dc985e66758_Traceguids);
            }
            try
            {
              v13 = std::wstring::wstring(v18, *((_QWORD *)v3 + 2));
              std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::insert<0,0>(
                v4 + 2,
                v17,
                v13);
              std::wstring::~wstring(v18);
            }
            catch ( ... )
            {
              v14 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u;
              if ( v14 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                WPP_RECORDER_AND_TRACE_SF_s(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  v14,
                  WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
                  *((_QWORD *)WPP_GLOBAL_Control + 5));
              return;
            }
          }
          return;
        }
        v8 = (unsigned int)(v8 + 1);
      }
    }
  }
  else if ( *((_DWORD *)a3 + 2) == 1 )
  {
    SetEvent(a2[1]);
  }
}

```

## disassembly

```asm
0x1800314f0  mov     [rsp+arg_0], rbx
0x1800314f5  mov     [rsp+arg_18], rsi
0x1800314fa  push    rdi
0x1800314fb  push    r12
0x1800314fd  push    r13
0x1800314ff  push    r14
0x180031501  push    r15
0x180031503  sub     rsp, 90h
0x18003150a  mov     rax, cs:__security_cookie
0x180031511  xor     rax, rsp
0x180031514  mov     [rsp+0B8h+var_38], rax
0x18003151c  mov     rbx, r8
0x18003151f  mov     rsi, rdx
0x180031522  mov     ecx, [r8]
0x180031525  test    ecx, ecx
0x180031527  jz      loc_1800316AB
0x18003152d  cmp     ecx, 1
0x180031530  jnz     loc_1800316C2
0x180031536  lea     r12, WPP_GLOBAL_Control
0x18003153d  mov     r10, cs:WPP_GLOBAL_Control
0x180031544  cmp     r10, r12
0x180031547  jz      short loc_180031557
0x180031549  cmp     byte ptr [r10+19h], 4
0x18003154e  jb      short loc_180031557
0x180031550  mov     edi, ecx
0x180031552  mov     dl, dil
0x180031555  jmp     short loc_18003155E
0x180031557  xor     dl, dl
0x180031559  mov     edi, 1
0x18003155e  lea     r13, WPP_RECORDER_INITIALIZED
0x180031565  mov     r9, cs:WPP_RECORDER_INITIALIZED
0x18003156c  cmp     r9, r13
0x18003156f  setnz   r8b
0x180031573  test    dl, dl
0x180031575  jnz     short loc_180031585
0x180031577  test    r8b, r8b
0x18003157a  jnz     short loc_180031585
0x18003157c  lea     r14, WPP_95fda3e624973c89daad3dc985e66758_Traceguids
0x180031583  jmp     short loc_1800315BC
0x180031585  mov     rax, [rbx+10h]
0x180031589  mov     [rsp+0B8h+var_70], rax
0x18003158e  lea     r14, WPP_95fda3e624973c89daad3dc985e66758_Traceguids
0x180031595  mov     [rsp+0B8h+var_80], r14
0x18003159a  mov     [rsp+0B8h+var_88], 29h ; ')'
0x1800315a1  mov     r9, [r10+28h]
0x1800315a5  mov     rcx, [r10+10h]
0x1800315a9  call    WPP_RECORDER_AND_TRACE_SF_sS
0x1800315ae  mov     r10, cs:WPP_GLOBAL_Control
0x1800315b5  mov     r9, cs:WPP_RECORDER_INITIALIZED
0x1800315bc  xor     edx, edx
0x1800315be  mov     r8d, cs:dword_18003EF20
0x1800315c5  mov     r11, qword ptr cs:DEVPKEY_BluetoothLE_PrepairingDeviceId+8
0x1800315cc  mov     r15, qword ptr cs:DEVPKEY_BluetoothLE_PrepairingDeviceId
0x1800315d3  cmp     edx, [rbx+18h]
0x1800315d6  jnb     loc_1800316A2
0x1800315dc  lea     rax, [rdx+rdx*2]
0x1800315e0  add     rax, rax
0x1800315e3  mov     rcx, [rbx+20h]
0x1800315e7  cmp     r15, [rcx+rax*8]
0x1800315eb  jnz     loc_1800316A4
0x1800315f1  cmp     r11, [rcx+rax*8+8]
0x1800315f6  jnz     loc_1800316A4
0x1800315fc  cmp     r8d, [rcx+rax*8+10h]
0x180031601  jnz     loc_1800316A4
0x180031607  cmp     dword ptr [rcx+rax*8+20h], 1003h
0x18003160f  jnz     loc_1800316A4
0x180031615  cmp     dword ptr [rcx+rax*8+24h], 8
0x18003161a  jnz     loc_1800316A4
0x180031620  mov     rdx, [rsi]
0x180031623  mov     rax, [rcx+rax*8+28h]
0x180031628  mov     rcx, [rax]
0x18003162b  cmp     rcx, [rdx+11h]
0x18003162f  jnz     short loc_1800316A2
0x180031631  cmp     r10, r12
0x180031634  jz      short loc_18003163D
0x180031636  cmp     byte ptr [r10+19h], 4
0x18003163b  jnb     short loc_180031640
0x18003163d  xor     dil, dil
0x180031640  cmp     r9, r13
0x180031643  setnz   r8b
0x180031647  test    dil, dil
0x18003164a  jnz     short loc_180031651
0x18003164c  test    r8b, r8b
0x18003164f  jz      short loc_180031676
0x180031651  mov     rax, [rbx+10h]
0x180031655  mov     [rsp+0B8h+var_70], rax
0x18003165a  mov     [rsp+0B8h+var_80], r14
0x18003165f  mov     [rsp+0B8h+var_88], 2Ah ; '*'
0x180031666  mov     r9, [r10+28h]
0x18003166a  mov     dl, dil
0x18003166d  mov     rcx, [r10+10h]
0x180031671  call    WPP_RECORDER_AND_TRACE_SF_sS
0x180031676  mov     rdx, [rbx+10h]
0x18003167a  lea     rcx, [rsp+0B8h+var_58]
0x18003167f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180031684  nop
0x180031685  mov     r8, rax
0x180031688  lea     rdx, [rsp+0B8h+var_68]
0x18003168d  lea     rcx, [rsi+10h]
0x180031691  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::insert<0,0>(std::wstring &&)
0x180031696  nop
0x180031697  lea     rcx, [rsp+0B8h+var_58]
0x18003169c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800316a1  nop
0x1800316a2  jmp     short loc_1800316C2
0x1800316a4  add     edx, edi
0x1800316a6  jmp     loc_1800315D3
0x1800316ab  cmp     dword ptr [r8+8], 1
0x1800316b0  jnz     short loc_1800316C2
0x1800316b2  mov     rcx, [rdx+8]; hEvent
0x1800316b6  call    cs:__imp_SetEvent
0x1800316bd  nop     dword ptr [rax+rax+00h]
0x1800316c2  mov     rcx, [rsp+0B8h+var_38]
0x1800316ca  xor     rcx, rsp; StackCookie
0x1800316cd  call    __security_check_cookie
0x1800316d2  lea     r11, [rsp+0B8h+var_28]
0x1800316da  mov     rbx, [r11+30h]
0x1800316de  mov     rsi, [r11+48h]
0x1800316e2  mov     rsp, r11
0x1800316e5  pop     r15
0x1800316e7  pop     r14
0x1800316e9  pop     r13
0x1800316eb  pop     r12
0x1800316ed  pop     rdi
0x1800316ee  retn
```
