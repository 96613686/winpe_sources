# KeyboardOverriderDispatcher::SendMessageToNarrator(_MIT_KEYBOARD_INPUT_MESSAGE const &,KeyboardInputInfo const &)

- ea: `0x1800b56d0`
- end: `0x1800b5c8c`
- name: `?SendMessageToNarrator@KeyboardOverriderDispatcher@@AEAAXAEBU_MIT_KEYBOARD_INPUT_MESSAGE@@AEBUKeyboardInputInfo@@@Z`
- size: `1468`
- prototype: `void __fastcall(KeyboardOverriderDispatcher *__hidden this, const struct _MIT_KEYBOARD_INPUT_MESSAGE *, const struct KeyboardInputInfo *)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1801307cc`
- `0x180130f20`

## callees

- `0x18008dcac`
- `0x1800b56d0`
- `0x1800b5c94`
- `0x1800b5cb4`
- `0x1800f0990`
- `0x180130550`
- `0x180170980`
- `0x1801ce010`

## import_xrefs

- `CoreMessaging!MsgBlobCreateShared` at `0x1800b57bb`
- `CoreMessaging!MsgBlobCreateShared` at `0x1800b57bb`
- `CoreMessaging!MsgStringCreateShared` at `0x1800b599d`
- `CoreMessaging!MsgStringCreateShared` at `0x1800b5a98`
- `CoreMessaging!MsgStringCreateShared` at `0x1800b599d`
- `CoreMessaging!MsgStringCreateShared` at `0x1800b5a98`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetForegroundWindow` at `0x1800b5b8d`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetForegroundWindow` at `0x1800b5b8d`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x1800b5b9d`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x1800b5b9d`
- `ext-ms-win-ntuser-keyboard-l1-1-0!GetKeyboardLayout` at `0x1800b5ba7`
- `ext-ms-win-ntuser-keyboard-l1-1-0!GetKeyboardLayout` at `0x1800b5ba7`
- `ext-ms-win-ntuser-keyboard-l1-1-0!ToUnicodeEx` at `0x1800b5bdc`
- `ext-ms-win-ntuser-keyboard-l1-1-0!ToUnicodeEx` at `0x1800b5bdc`

## string_xrefs

- `0x1800b59b1`: `onecoreuap\windows\moderncore\inputv2\systeminputhosts\components\win32kinterop\lib\keyboardoverriderdispatcher.cpp`
- `0x1800b5a13`: `onecoreuap\windows\moderncore\inputv2\systeminputhosts\components\win32kinterop\lib\keyboardoverriderdispatcher.cpp`
- `0x1800b5aac`: `onecoreuap\windows\moderncore\inputv2\systeminputhosts\components\win32kinterop\lib\keyboardoverriderdispatcher.cpp`
- `0x1800b5b14`: `onecoreuap\windows\moderncore\inputv2\systeminputhosts\components\win32kinterop\lib\keyboardoverriderdispatcher.cpp`
- `0x1800b5b7a`: `onecoreuap\windows\moderncore\inputv2\systeminputhosts\components\win32kinterop\lib\keyboardoverriderdispatcher.cpp`
- `0x1800b5c7a`: `onecoreuap\windows\moderncore\inputv2\systeminputhosts\components\win32kinterop\lib\keyboardoverriderdispatcher.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall KeyboardOverriderDispatcher::SendMessageToNarrator(
        KeyboardOverriderDispatcher *this,
        const struct _MIT_KEYBOARD_INPUT_MESSAGE *a2,
        const struct KeyboardInputInfo *a3)
{
  _OWORD *KeyboardEvent; // rax
  int *v7; // rcx
  __int64 v8; // rdx
  __int16 v9; // ax
  unsigned int v10; // edi
  __int64 v11; // r8
  __int64 v12; // r9
  _OWORD *v13; // rax
  int *v14; // rcx
  __int64 v15; // r10
  __int64 v16; // rax
  unsigned __int64 v17; // rcx
  int Shared; // eax
  int v19; // eax
  void *v20; // rcx
  int v21; // eax
  int v22; // eax
  int v23; // eax
  DWORD WindowThreadProcessId; // edi
  HWND ForegroundWindow; // rax
  HKL dwhkl; // rax
  __int16 v27; // di
  WCHAR v28; // cx
  __int64 v29; // r10
  __int64 (__fastcall *v30)(__int64, _QWORD, _QWORD, _QWORD); // r11
  WCHAR *v31; // rax
  int v32; // edx
  int v33; // eax
  int cchBuff; // [rsp+20h] [rbp-E0h]
  int cchBuffa; // [rsp+20h] [rbp-E0h]
  int cchBuffb; // [rsp+20h] [rbp-E0h]
  int cchBuffc; // [rsp+20h] [rbp-E0h]
  int cchBuffd; // [rsp+20h] [rbp-E0h]
  int cchBuffe; // [rsp+20h] [rbp-E0h]
  WCHAR pwszBuff[2]; // [rsp+50h] [rbp-B0h] BYREF
  bool v41; // [rsp+54h] [rbp-ACh] BYREF
  int v42[2]; // [rsp+58h] [rbp-A8h] BYREF
  int v43[2]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR *v44; // [rsp+68h] [rbp-98h]
  _BYTE v45[304]; // [rsp+70h] [rbp-90h] BYREF
  int v46; // [rsp+1A0h] [rbp+A0h] BYREF
  unsigned __int16 v47; // [rsp+1A8h] [rbp+A8h]
  unsigned __int64 v48; // [rsp+1B0h] [rbp+B0h]
  __int64 v49; // [rsp+1B8h] [rbp+B8h]
  unsigned __int16 v50[4]; // [rsp+2D0h] [rbp+1D0h] BYREF
  _OWORD v51[2]; // [rsp+2D8h] [rbp+1D8h] BYREF
  __int64 v52; // [rsp+2F8h] [rbp+1F8h]
  wil::details::in1diag3 *retaddr; // [rsp+338h] [rbp+238h]

  if ( !*((_BYTE *)this + 704) )
  {
    *((_BYTE *)this + 704) = 1;
    KeyboardEvent = (_OWORD *)InputServiceProcessor::CreateKeyboardEvent(v45, a3);
    v7 = &v46;
    v8 = 2;
    do
    {
      *(_OWORD *)v7 = *KeyboardEvent;
      *((_OWORD *)v7 + 1) = KeyboardEvent[1];
      *((_OWORD *)v7 + 2) = KeyboardEvent[2];
      *((_OWORD *)v7 + 3) = KeyboardEvent[3];
      *((_OWORD *)v7 + 4) = KeyboardEvent[4];
      *((_OWORD *)v7 + 5) = KeyboardEvent[5];
      *((_OWORD *)v7 + 6) = KeyboardEvent[6];
      *((_OWORD *)v7 + 7) = KeyboardEvent[7];
      v7 += 32;
      KeyboardEvent += 8;
      --v8;
    }
    while ( v8 );
    *(_OWORD *)v7 = *KeyboardEvent;
    *((_OWORD *)v7 + 1) = KeyboardEvent[1];
    *((_QWORD *)v7 + 4) = *((_QWORD *)KeyboardEvent + 4);
    *(_QWORD *)v42 = 0;
    MsgBlobCreateShared((char *)this + 448, 256, v42);
    if ( v46 )
    {
      if ( v46 == 1 )
      {
        cchBuffd = v42[0];
        v23 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64))(**((_QWORD **)this + 55) + 32LL))(
                *((_QWORD *)this + 55),
                v47,
                WORD1(v48),
                v49);
        if ( v23 < 0 )
          wil::details::in1diag3::FailFast_Hr(
            retaddr,
            (void *)0x100,
            (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputhosts\\components\\win32kinterop\\lib\\ke"
                          "yboardoverriderdispatcher.cpp",
            (const char *)(unsigned int)v23,
            cchBuffd);
      }
      else if ( v46 == 2 )
      {
        v9 = *((_WORD *)a2 + 135);
        if ( (v9 & 0x100) != 0 )
        {
          std::deque<KeyboardEvent>::_Emplace_back_internal<KeyboardEvent const &>((char *)this + 712, &v46);
          (*(void (__fastcall **)(KeyboardOverriderDispatcher *, _QWORD))(*(_QWORD *)this + 32LL))(this, 0);
        }
        else
        {
          if ( (v9 & 0x200) != 0 )
          {
            memset(v51, 0, sizeof(v51));
            v52 = 0;
            v10 = 0;
            std::deque<KeyboardEvent>::_Emplace_back_internal<KeyboardEvent const &>((char *)this + 712, &v46);
            while ( 1 )
            {
              v11 = *((_QWORD *)this + 93);
              if ( !v11 || v10 >= 0x14 )
                break;
              v12 = *((_QWORD *)this + 92);
              v13 = *(_OWORD **)(*((_QWORD *)this + 90) + 8 * (v12 & (*((_QWORD *)this + 91) - 1LL)));
              v14 = &v46;
              v15 = 2;
              do
              {
                *(_OWORD *)v14 = *v13;
                *((_OWORD *)v14 + 1) = v13[1];
                *((_OWORD *)v14 + 2) = v13[2];
                *((_OWORD *)v14 + 3) = v13[3];
                *((_OWORD *)v14 + 4) = v13[4];
                *((_OWORD *)v14 + 5) = v13[5];
                *((_OWORD *)v14 + 6) = v13[6];
                *((_OWORD *)v14 + 7) = v13[7];
                v14 += 32;
                v13 += 8;
                --v15;
              }
              while ( v15 );
              *(_OWORD *)v14 = *v13;
              *((_OWORD *)v14 + 1) = v13[1];
              *((_QWORD *)v14 + 4) = *((_QWORD *)v13 + 4);
              *((_QWORD *)this + 93) = v11 - 1;
              v16 = 0;
              if ( v11 != 1 )
                v16 = v12 + 1;
              *((_QWORD *)this + 92) = v16;
              LOWORD(v17) = 0;
              if ( v46 == 2 )
                v17 = HIDWORD(v48);
              if ( (v47 & 1) != 0 )
              {
                if ( (_WORD)v17 )
                  *((_WORD *)v51 + (int)v10++) = v17;
              }
            }
            *(_QWORD *)v50 = 0;
            Shared = MsgStringCreateShared(v51, v10, v50);
            if ( Shared < 0 )
              wil::details::in1diag3::FailFast_Hr(
                retaddr,
                (void *)0xD0,
                (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputhosts\\components\\win32kinterop\\lib"
                              "\\keyboardoverriderdispatcher.cpp",
                (const char *)(unsigned int)Shared,
                cchBuff);
            cchBuffa = *(_DWORD *)v50;
            v19 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64))(**((_QWORD **)this + 55) + 40LL))(
                    *((_QWORD *)this + 55),
                    5,
                    231);
            if ( v19 < 0 )
              wil::details::in1diag3::FailFast_Hr(
                retaddr,
                (void *)0xD9,
                (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputhosts\\components\\win32kinterop\\lib"
                              "\\keyboardoverriderdispatcher.cpp",
                (const char *)(unsigned int)v19,
                cchBuffa);
            v20 = v50;
          }
          else
          {
            *(_DWORD *)v50 = 0;
            v50[2] = 0;
            *(_DWORD *)pwszBuff = 0;
            SurrogateCharAccumulator::OnKey(
              (KeyboardOverriderDispatcher *)((char *)this + 434),
              *((_WORD *)a2 + 138),
              (v47 & 4) != 0,
              &v41,
              v50,
              (int *)pwszBuff);
            *(_QWORD *)v43 = 0;
            v21 = MsgStringCreateShared(v50, *(unsigned int *)pwszBuff, v43);
            if ( v21 < 0 )
              wil::details::in1diag3::FailFast_Hr(
                retaddr,
                (void *)0xED,
                (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputhosts\\components\\win32kinterop\\lib"
                              "\\keyboardoverriderdispatcher.cpp",
                (const char *)(unsigned int)v21,
                cchBuffb);
            cchBuffc = v43[0];
            v22 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, _QWORD))(**((_QWORD **)this + 55) + 40LL))(
                    *((_QWORD *)this + 55),
                    v47,
                    231,
                    (unsigned __int16)v48);
            if ( v22 < 0 )
              wil::details::in1diag3::FailFast_Hr(
                retaddr,
                (void *)0xF6,
                (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputhosts\\components\\win32kinterop\\lib"
                              "\\keyboardoverriderdispatcher.cpp",
                (const char *)(unsigned int)v22,
                cchBuffc);
            v20 = v43;
          }
          wil::details::unique_storage<wil::details::resource_policy<MsgBlob *,void (*)(MsgBuffer *),&void MsgRelease(MsgBuffer *),wistd::integral_constant<unsigned __int64,0>,MsgBlob *,MsgBlob *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<MsgBlob *,void (*)(MsgBuffer *),&void MsgRelease(MsgBuffer *),wistd::integral_constant<unsigned __int64,0>,MsgBlob *,MsgBlob *,0,std::nullptr_t>>(v20);
        }
      }
    }
    else
    {
      WindowThreadProcessId = 0;
      ForegroundWindow = GetForegroundWindow();
      if ( ForegroundWindow )
        WindowThreadProcessId = GetWindowThreadProcessId(ForegroundWindow, 0);
      dwhkl = GetKeyboardLayout(WindowThreadProcessId);
      *(_DWORD *)pwszBuff = 0;
      v27 = v48;
      if ( ToUnicodeEx(
             *((unsigned __int16 *)a3 + 30),
             (unsigned __int16)v48,
             (const BYTE *)this + 448,
             pwszBuff,
             1,
             4u,
             dwhkl) == 1 )
      {
        v28 = pwszBuff[0];
      }
      else
      {
        v28 = 0;
        pwszBuff[0] = 0;
      }
      v29 = *((_QWORD *)this + 55);
      v30 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v29 + 24LL);
      v31 = pwszBuff;
      v44 = pwszBuff;
      v32 = 0;
      if ( v28 )
      {
        do
        {
          ++v31;
          ++v32;
        }
        while ( *v31 );
      }
      v43[0] = v32 | 0x80000000;
      LOWORD(cchBuffe) = v27;
      v33 = v30(v29, HIWORD(v48), v47, *((unsigned __int16 *)a3 + 30));
      if ( v33 < 0 )
        wil::details::in1diag3::FailFast_Hr(
          retaddr,
          (void *)0x11B,
          (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputhosts\\components\\win32kinterop\\lib\\keyb"
                        "oardoverriderdispatcher.cpp",
          (const char *)(unsigned int)v33,
          cchBuffe);
    }
    wil::details::unique_storage<wil::details::resource_policy<MsgBlob *,void (*)(MsgBuffer *),&void MsgRelease(MsgBuffer *),wistd::integral_constant<unsigned __int64,0>,MsgBlob *,MsgBlob *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<MsgBlob *,void (*)(MsgBuffer *),&void MsgRelease(MsgBuffer *),wistd::integral_constant<unsigned __int64,0>,MsgBlob *,MsgBlob *,0,std::nullptr_t>>(v42);
  }
}

```

## disassembly

```asm
0x1800b56d0  mov     [rsp-8+arg_8], rbx
0x1800b56d5  mov     [rsp-8+arg_18], rsi
0x1800b56da  push    rbp
0x1800b56db  push    rdi
0x1800b56dc  push    r12
0x1800b56de  push    r14
0x1800b56e0  push    r15
0x1800b56e2  lea     rbp, [rsp-210h]
0x1800b56ea  sub     rsp, 310h
0x1800b56f1  mov     rax, cs:__security_cookie
0x1800b56f8  xor     rax, rsp
0x1800b56fb  mov     [rbp+230h+var_30], rax
0x1800b5702  mov     rsi, r8
0x1800b5705  mov     rdi, rdx
0x1800b5708  mov     rbx, rcx
0x1800b570b  xor     r15d, r15d
0x1800b570e  cmp     [rcx+2C0h], r15b
0x1800b5715  jnz     loc_1800B5819
0x1800b571b  mov     byte ptr [rcx+2C0h], 1
0x1800b5722  mov     rdx, r8
0x1800b5725  lea     rcx, [rsp+330h+var_2C0]
0x1800b572a  call    ?CreateKeyboardEvent@InputServiceProcessor@@SA?AUKeyboardEvent@@QEBUKeyboardInputInfo@@@Z; InputServiceProcessor::CreateKeyboardEvent(KeyboardInputInfo const * const)
0x1800b572f  lea     rcx, [rbp+230h+var_190]
0x1800b5736  lea     edx, [r15+2]
0x1800b573a  lea     r8d, [rdx+7Eh]
0x1800b573e  movups  xmm0, xmmword ptr [rax]
0x1800b5741  movups  xmmword ptr [rcx], xmm0
0x1800b5744  movups  xmm1, xmmword ptr [rax+10h]
0x1800b5748  movups  xmmword ptr [rcx+10h], xmm1
0x1800b574c  movups  xmm0, xmmword ptr [rax+20h]
0x1800b5750  movups  xmmword ptr [rcx+20h], xmm0
0x1800b5754  movups  xmm1, xmmword ptr [rax+30h]
0x1800b5758  movups  xmmword ptr [rcx+30h], xmm1
0x1800b575c  movups  xmm0, xmmword ptr [rax+40h]
0x1800b5760  movups  xmmword ptr [rcx+40h], xmm0
0x1800b5764  movups  xmm1, xmmword ptr [rax+50h]
0x1800b5768  movups  xmmword ptr [rcx+50h], xmm1
0x1800b576c  movups  xmm0, xmmword ptr [rax+60h]
0x1800b5770  movups  xmmword ptr [rcx+60h], xmm0
0x1800b5774  movups  xmm1, xmmword ptr [rax+70h]
0x1800b5778  movups  xmmword ptr [rcx+70h], xmm1
0x1800b577c  add     rcx, r8
0x1800b577f  add     rax, r8
0x1800b5782  sub     rdx, 1
0x1800b5786  jnz     short loc_1800B573E
0x1800b5788  movups  xmm0, xmmword ptr [rax]
0x1800b578b  movups  xmmword ptr [rcx], xmm0
0x1800b578e  movups  xmm1, xmmword ptr [rax+10h]
0x1800b5792  movups  xmmword ptr [rcx+10h], xmm1
0x1800b5796  mov     rax, [rax+20h]
0x1800b579a  mov     [rcx+20h], rax
0x1800b579e  mov     qword ptr [rsp+330h+var_2D8], r15
0x1800b57a3  lea     r14, [rbx+1C0h]
0x1800b57aa  lea     r8, [rsp+330h+var_2D8]
0x1800b57af  mov     r12d, 100h
0x1800b57b5  mov     edx, r12d
0x1800b57b8  mov     rcx, r14
0x1800b57bb  call    cs:__imp_MsgBlobCreateShared
0x1800b57c1  mov     ecx, [rbp+230h+var_190]
0x1800b57c7  test    ecx, ecx
0x1800b57c9  jz      loc_1800B5B8A
0x1800b57cf  sub     ecx, 1
0x1800b57d2  jz      loc_1800B5B35
0x1800b57d8  cmp     ecx, 1
0x1800b57db  jnz     short loc_1800B580F
0x1800b57dd  movzx   eax, word ptr [rdi+10Eh]
0x1800b57e4  test    r12w, ax
0x1800b57e8  jz      short loc_1800B5844
0x1800b57ea  lea     rcx, [rbx+2C8h]
0x1800b57f1  lea     rdx, [rbp+230h+var_190]
0x1800b57f8  call    ??$_Emplace_back_internal@AEBUKeyboardEvent@@@?$deque@UKeyboardEvent@@V?$allocator@UKeyboardEvent@@@std@@@std@@AEAAXAEBUKeyboardEvent@@@Z; std::deque<KeyboardEvent>::_Emplace_back_internal<KeyboardEvent const &>(KeyboardEvent const &)
0x1800b57fd  mov     rax, [rbx]
0x1800b5800  xor     edx, edx
0x1800b5802  mov     rcx, rbx
0x1800b5805  mov     rax, [rax+20h]
0x1800b5809  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b580e  nop
0x1800b580f  lea     rcx, [rsp+330h+var_2D8]
0x1800b5814  call    ??1?$unique_storage@U?$resource_policy@PEAUMsgBlob@@P6AXPEAUMsgBuffer@@@Z$1?MsgRelease@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<MsgBlob *,void (*)(MsgBuffer *),&MsgRelease(MsgBuffer *),wistd::integral_constant<unsigned __int64,0>,MsgBlob *,MsgBlob *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<MsgBlob *,void (*)(MsgBuffer *),&MsgRelease(MsgBuffer *),wistd::integral_constant<unsigned __int64,0>,MsgBlob *,MsgBlob *,0,std::nullptr_t>>(void)
0x1800b5819  mov     rcx, [rbp+230h+var_30]
0x1800b5820  xor     rcx, rsp; StackCookie
0x1800b5823  call    __security_check_cookie
0x1800b5828  lea     r11, [rsp+330h+var_20]
0x1800b5830  mov     rbx, [r11+38h]
0x1800b5834  mov     rsi, [r11+48h]
0x1800b5838  mov     rsp, r11
0x1800b583b  pop     r15
0x1800b583d  pop     r14
0x1800b583f  pop     r12
0x1800b5841  pop     rdi
0x1800b5842  pop     rbp
0x1800b5843  retn
0x1800b5844  bt      ax, 9
0x1800b5849  jnb     loc_1800B5A31
0x1800b584f  xorps   xmm0, xmm0
0x1800b5852  xor     eax, eax
0x1800b5854  movups  [rbp+230h+var_58], xmm0
0x1800b585b  movups  [rbp+230h+var_48], xmm0
0x1800b5862  mov     [rbp+230h+var_38], rax
0x1800b5869  mov     edi, r15d
0x1800b586c  lea     rcx, [rbx+2C8h]
0x1800b5873  lea     rdx, [rbp+230h+var_190]
0x1800b587a  call    ??$_Emplace_back_internal@AEBUKeyboardEvent@@@?$deque@UKeyboardEvent@@V?$allocator@UKeyboardEvent@@@std@@@std@@AEAAXAEBUKeyboardEvent@@@Z; std::deque<KeyboardEvent>::_Emplace_back_internal<KeyboardEvent const &>(KeyboardEvent const &)
0x1800b587f  mov     r11d, 80h
0x1800b5885  mov     r8, [rbx+2E8h]
0x1800b588c  test    r8, r8
0x1800b588f  jz      loc_1800B5986
0x1800b5895  cmp     edi, 14h
0x1800b5898  jnb     loc_1800B5986
0x1800b589e  lea     rdx, [rbx+2E0h]
0x1800b58a5  mov     r9, [rdx]
0x1800b58a8  mov     rcx, [rbx+2D8h]
0x1800b58af  dec     rcx
0x1800b58b2  and     rcx, r9
0x1800b58b5  mov     rax, [rbx+2D0h]
0x1800b58bc  mov     rax, [rax+rcx*8]
0x1800b58c0  lea     rcx, [rbp+230h+var_190]
0x1800b58c7  mov     r10d, 2
0x1800b58cd  movups  xmm0, xmmword ptr [rax]
0x1800b58d0  movups  xmmword ptr [rcx], xmm0
0x1800b58d3  movups  xmm1, xmmword ptr [rax+10h]
0x1800b58d7  movups  xmmword ptr [rcx+10h], xmm1
0x1800b58db  movups  xmm0, xmmword ptr [rax+20h]
0x1800b58df  movups  xmmword ptr [rcx+20h], xmm0
0x1800b58e3  movups  xmm1, xmmword ptr [rax+30h]
0x1800b58e7  movups  xmmword ptr [rcx+30h], xmm1
0x1800b58eb  movups  xmm0, xmmword ptr [rax+40h]
0x1800b58ef  movups  xmmword ptr [rcx+40h], xmm0
0x1800b58f3  movups  xmm1, xmmword ptr [rax+50h]
0x1800b58f7  movups  xmmword ptr [rcx+50h], xmm1
0x1800b58fb  movups  xmm0, xmmword ptr [rax+60h]
0x1800b58ff  movups  xmmword ptr [rcx+60h], xmm0
0x1800b5903  movups  xmm1, xmmword ptr [rax+70h]
0x1800b5907  movups  xmmword ptr [rcx+70h], xmm1
0x1800b590b  add     rcx, r11
0x1800b590e  add     rax, r11
0x1800b5911  sub     r10, 1
0x1800b5915  jnz     short loc_1800B58CD
0x1800b5917  movups  xmm0, xmmword ptr [rax]
0x1800b591a  movups  xmmword ptr [rcx], xmm0
0x1800b591d  movups  xmm1, xmmword ptr [rax+10h]
0x1800b5921  movups  xmmword ptr [rcx+10h], xmm1
0x1800b5925  mov     rax, [rax+20h]
0x1800b5929  mov     [rcx+20h], rax
0x1800b592d  lea     rax, [r8-1]
0x1800b5931  mov     [rbx+2E8h], rax
0x1800b5938  test    rax, rax
0x1800b593b  mov     rax, r15
0x1800b593e  jz      short loc_1800B5944
0x1800b5940  lea     rax, [r9+1]
0x1800b5944  mov     [rdx], rax
0x1800b5947  mov     ecx, r15d
0x1800b594a  cmp     [rbp+230h+var_190], 2
0x1800b5951  jnz     short loc_1800B595E
0x1800b5953  mov     rcx, [rbp+230h+var_180]
0x1800b595a  shr     rcx, 20h
0x1800b595e  test    byte ptr [rbp+230h+var_188], 1
0x1800b5965  jz      loc_1800B5885
0x1800b596b  test    cx, cx
0x1800b596e  jz      loc_1800B5885
0x1800b5974  movsxd  rax, edi
0x1800b5977  mov     word ptr [rbp+rax*2+230h+var_58], cx
0x1800b597f  inc     edi
0x1800b5981  jmp     loc_1800B5885
0x1800b5986  mov     qword ptr [rbp+230h+var_60], r15
0x1800b598d  lea     r8, [rbp+230h+var_60]
0x1800b5994  mov     edx, edi
0x1800b5996  lea     rcx, [rbp+230h+var_58]
0x1800b599d  call    cs:__imp_MsgStringCreateShared
0x1800b59a3  mov     rcx, [rbp+238h]; this
0x1800b59aa  test    eax, eax
0x1800b59ac  jns     short loc_1800B59C3
0x1800b59ae  mov     r9d, eax; char *
0x1800b59b1  lea     r8, aOnecoreuapWind_20; "onecoreuap\\windows\\moderncore\\inputv"...
0x1800b59b8  mov     edx, 0D0h; void *
0x1800b59bd  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x1800b59c3  mov     rcx, [rbx+1B8h]
0x1800b59ca  mov     rbx, qword ptr [rsp+330h+var_2D8]
0x1800b59cf  mov     rdi, qword ptr [rbp+230h+var_60]
0x1800b59d6  mov     rax, [rcx]
0x1800b59d9  xor     r9d, r9d
0x1800b59dc  lea     edx, [r9+5]
0x1800b59e0  mov     r8d, 0E7h
0x1800b59e6  mov     [rsp+330h+var_2F8], rbx
0x1800b59eb  mov     word ptr [rsp+330h+dwhkl], r15w
0x1800b59f1  mov     word ptr [rsp+330h+wFlags], r15w
0x1800b59f7  mov     qword ptr [rsp+330h+cchBuff], rdi; int
0x1800b59fc  mov     rax, [rax+28h]
0x1800b5a00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b5a05  mov     rcx, [rbp+238h]; this
0x1800b5a0c  test    eax, eax
0x1800b5a0e  jns     short loc_1800B5A25
0x1800b5a10  mov     r9d, eax; char *
0x1800b5a13  lea     r8, aOnecoreuapWind_20; "onecoreuap\\windows\\moderncore\\inputv"...
0x1800b5a1a  mov     edx, 0D9h; void *
0x1800b5a1f  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x1800b5a25  lea     rcx, [rbp+230h+var_60]
0x1800b5a2c  jmp     loc_1800B5B2B
0x1800b5a31  xor     eax, eax
0x1800b5a33  mov     dword ptr [rbp+230h+var_60], eax
0x1800b5a39  mov     [rbp+230h+var_60+4], ax
0x1800b5a40  mov     dword ptr [rsp+330h+pwszBuff], r15d
0x1800b5a45  mov     r8b, byte ptr [rbp+230h+var_188]
0x1800b5a4c  shr     r8b, 2
0x1800b5a50  and     r8b, 1; bool
0x1800b5a54  lea     rcx, [rbx+1B2h]; this
0x1800b5a5b  lea     rax, [rsp+330h+pwszBuff]
0x1800b5a60  mov     qword ptr [rsp+330h+wFlags], rax; int *
0x1800b5a65  lea     rax, [rbp+230h+var_60]
0x1800b5a6c  mov     qword ptr [rsp+330h+cchBuff], rax; int
0x1800b5a71  lea     r9, [rsp+330h+var_2DC]; bool *
0x1800b5a76  movzx   edx, word ptr [rdi+114h]; unsigned __int16
0x1800b5a7d  call    ?OnKey@SurrogateCharAccumulator@@QEAAXG_NAEA_NQEAGAEAH@Z; SurrogateCharAccumulator::OnKey(ushort,bool,bool &,ushort * const,int &)
0x1800b5a82  nop
0x1800b5a83  mov     qword ptr [rsp+330h+var_2D0], r15
0x1800b5a88  lea     r8, [rsp+330h+var_2D0]
0x1800b5a8d  mov     edx, dword ptr [rsp+330h+pwszBuff]
0x1800b5a91  lea     rcx, [rbp+230h+var_60]
0x1800b5a98  call    cs:__imp_MsgStringCreateShared
0x1800b5a9e  mov     rcx, [rbp+238h]; this
0x1800b5aa5  test    eax, eax
0x1800b5aa7  jns     short loc_1800B5ABE
0x1800b5aa9  mov     r9d, eax; char *
0x1800b5aac  lea     r8, aOnecoreuapWind_20; "onecoreuap\\windows\\moderncore\\inputv"...
0x1800b5ab3  mov     edx, 0EDh; void *
0x1800b5ab8  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x1800b5abe  mov     rcx, [rbx+1B8h]
0x1800b5ac5  mov     r11, qword ptr [rsp+330h+var_2D8]
0x1800b5aca  mov     rbx, qword ptr [rsp+330h+var_2D0]
0x1800b5acf  mov     rax, [rcx]
0x1800b5ad2  mov     r8d, 0E7h
0x1800b5ad8  mov     [rsp+330h+var_2F8], r11
0x1800b5add  mov     word ptr [rsp+330h+dwhkl], r15w
0x1800b5ae3  mov     word ptr [rsp+330h+wFlags], r15w
0x1800b5ae9  mov     qword ptr [rsp+330h+cchBuff], rbx; int
0x1800b5aee  movzx   r9d, word ptr [rbp+230h+var_180]
0x1800b5af6  movzx   edx, [rbp+230h+var_188]
0x1800b5afd  mov     rax, [rax+28h]
0x1800b5b01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b5b06  mov     rcx, [rbp+238h]; this
0x1800b5b0d  test    eax, eax
0x1800b5b0f  jns     short loc_1800B5B26
0x1800b5b11  mov     r9d, eax; char *
0x1800b5b14  lea     r8, aOnecoreuapWind_20; "onecoreuap\\windows\\moderncore\\inputv"...
0x1800b5b1b  mov     edx, 0F6h; void *
0x1800b5b20  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x1800b5b26  lea     rcx, [rsp+330h+var_2D0]
0x1800b5b2b  call    ??1?$unique_storage@U?$resource_policy@PEAUMsgBlob@@P6AXPEAUMsgBuffer@@@Z$1?MsgRelease@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<MsgBlob *,void (*)(MsgBuffer *),&MsgRelease(MsgBuffer *),wistd::integral_constant<unsigned __int64,0>,MsgBlob *,MsgBlob *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<MsgBlob *,void (*)(MsgBuffer *),&MsgRelease(MsgBuffer *),wistd::integral_constant<unsigned __int64,0>,MsgBlob *,MsgBlob *,0,std::nullptr_t>>(void)
0x1800b5b30  jmp     loc_1800B580F
0x1800b5b35  mov     rcx, [rbx+1B8h]
0x1800b5b3c  mov     rdx, qword ptr [rsp+330h+var_2D8]
0x1800b5b41  mov     rax, [rcx]
0x1800b5b44  mov     qword ptr [rsp+330h+cchBuff], rdx; int
0x1800b5b49  mov     r9, [rbp+230h+var_178]
0x1800b5b50  movzx   r8d, word ptr [rbp+230h+var_180+2]
0x1800b5b58  movzx   edx, [rbp+230h+var_188]
0x1800b5b5f  mov     rax, [rax+20h]
0x1800b5b63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b5b68  mov     rcx, [rbp+238h]; this
0x1800b5b6f  test    eax, eax
0x1800b5b71  jns     loc_1800B580F
0x1800b5b77  mov     r9d, eax; char *
0x1800b5b7a  lea     r8, aOnecoreuapWind_20; "onecoreuap\\windows\\moderncore\\inputv"...
0x1800b5b81  mov     edx, r12d; void *
0x1800b5b84  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x1800b5b8a  mov     edi, r15d
0x1800b5b8d  call    cs:__imp_GetForegroundWindow
0x1800b5b93  test    rax, rax
0x1800b5b96  jz      short loc_1800B5BA5
0x1800b5b98  xor     edx, edx; lpdwProcessId
0x1800b5b9a  mov     rcx, rax; hWnd
0x1800b5b9d  call    cs:__imp_GetWindowThreadProcessId
0x1800b5ba3  mov     edi, eax
0x1800b5ba5  mov     ecx, edi; idThread
0x1800b5ba7  call    cs:__imp_GetKeyboardLayout
0x1800b5bad  mov     dword ptr [rsp+330h+pwszBuff], r15d
0x1800b5bb2  movzx   edi, word ptr [rbp+230h+var_180]
0x1800b5bb9  mov     edx, edi; wScanCode
0x1800b5bbb  movzx   ecx, word ptr [rsi+3Ch]; wVirtKey
0x1800b5bbf  mov     [rsp+330h+dwhkl], rax; dwhkl
0x1800b5bc4  mov     [rsp+330h+wFlags], 4; wFlags
0x1800b5bcc  mov     [rsp+330h+cchBuff], 1; cchBuff
0x1800b5bd4  lea     r9, [rsp+330h+pwszBuff]; pwszBuff
0x1800b5bd9  mov     r8, r14; lpKeyState
0x1800b5bdc  call    cs:__imp_ToUnicodeEx
0x1800b5be2  cmp     eax, 1
0x1800b5be5  jz      short loc_1800B5BF1
0x1800b5be7  mov     ecx, r15d
0x1800b5bea  mov     [rsp+330h+pwszBuff], cx
0x1800b5bef  jmp     short loc_1800B5BF6
0x1800b5bf1  movzx   ecx, [rsp+330h+pwszBuff]
0x1800b5bf6  mov     r10, [rbx+1B8h]
0x1800b5bfd  mov     rax, [r10]
0x1800b5c00  mov     r11, [rax+18h]
0x1800b5c04  mov     r8, qword ptr [rsp+330h+var_2D8]
0x1800b5c09  lea     rax, [rsp+330h+pwszBuff]
0x1800b5c0e  lea     rdx, [rsp+330h+pwszBuff]
0x1800b5c13  mov     [rsp+330h+var_2C8], rdx
0x1800b5c18  mov     rdx, r15
0x1800b5c1b  test    cx, cx
  ... truncated ...
```
