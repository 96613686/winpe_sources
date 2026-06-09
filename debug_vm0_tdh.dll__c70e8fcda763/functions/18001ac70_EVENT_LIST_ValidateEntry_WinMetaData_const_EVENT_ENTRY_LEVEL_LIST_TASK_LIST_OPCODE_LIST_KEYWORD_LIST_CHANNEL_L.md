# EVENT_LIST::ValidateEntry(WinMetaData const &,EVENT_ENTRY *,LEVEL_LIST &,TASK_LIST &,OPCODE_LIST &,KEYWORD_LIST &,CHANNEL_LIST &,TEMPLATE_LIST &,TASK_LIST::TASK_ENTRY_MAP &,std::map<std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,TEMPLATE_ENTRY *,std::less<std::basic_string_view<wchar_t,std::char_traits<wchar_t>>>,std::allocator<std::pair<std::basic_string_view<wchar_t,std::char_traits<wchar_t>> const,TEMPLATE_ENTRY *>>> &,ETW_PROVIDER_ENTRY &)

- ea: `0x18001ac70`
- end: `0x18001b032`
- name: `?ValidateEntry@EVENT_LIST@@AEAAXAEBVWinMetaData@@PEAVEVENT_ENTRY@@AEAVLEVEL_LIST@@AEAVTASK_LIST@@AEAVOPCODE_LIST@@AEAVKEYWORD_LIST@@AEAVCHANNEL_LIST@@AEAVTEMPLATE_LIST@@AEAUTASK_ENTRY_MAP@5@AEAV?$map@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@PEAVTEMPLATE_ENTRY@@U?$less@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@PEAVTEMPLATE_ENTRY@@@std@@@2@@std@@AEAVETW_PROVIDER_ENTRY@@@Z`
- size: `962`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `service_task`

## callers

- `0x18001c5e4`

## callees

- `0x180019ec4`
- `0x18001ac70`
- `0x18001b340`
- `0x18001b6f0`
- `0x18001bdb8`
- `0x18001c300`
- `0x18001c440`
- `0x18001ed1c`
- `0x180021490`
- `0x18002fb7c`
- `0x180033f84`
- `0x18003410c`
- `0x1800342ec`

## pseudocode

```c
void __fastcall EVENT_LIST::ValidateEntry(
        __int64 a1,
        struct WinMetaData *a2,
        unsigned int *a3,
        __int64 a4,
        int a5,
        __int64 a6,
        __int64 a7,
        CHANNEL_LIST *a8,
        __int64 a9,
        int a10,
        __int64 a11,
        __int64 a12)
{
  unsigned int *v13; // r8
  _QWORD *v15; // rbx
  int v16; // eax
  _QWORD *v17; // rdx
  _QWORD *v18; // rcx
  _QWORD *v19; // rdx
  unsigned __int64 v20; // rsi
  _QWORD *v21; // rdx
  __int64 v22; // r15
  __int64 v23; // rdx
  unsigned __int64 v24; // rcx
  __int64 v25; // rax
  size_t v26; // rbx
  __int64 i; // r14
  EVENT_LIST *v28; // rcx
  __int64 v29; // rbx
  _QWORD *v30; // rcx
  __int64 v31; // rdx
  bool v32; // zf
  _QWORD *v33; // rdx
  _QWORD *v34; // rdx
  __int64 v35; // rax
  _QWORD *v36; // rdx
  _QWORD *v37; // rdx

  v13 = a3 + 26;
  if ( *((_QWORD *)v13 + 2) )
    LEVEL_LIST::AddRef(a4, a2, v13, a12, a3 + 84);
  if ( *((_QWORD *)a3 + 23) )
    TASK_LIST::AddRefFast(a5, (_DWORD)a2, (_DWORD)a3 + 168, a10, a12, (__int64)(a3 + 86));
  v15 = a3 + 34;
  if ( *((_QWORD *)a3 + 19) )
  {
    v16 = OPCODE_LIST::AddRef(a6, a2, a3 + 34, a12, a3 + 88, *((_QWORD *)a3 + 43));
    if ( v16 == -1073221754 )
    {
      v18 = *(_QWORD **)(*((_QWORD *)a3 + 44) + 128LL);
      if ( v18[3] > 7u )
        v18 = (_QWORD *)*v18;
      if ( *((_QWORD *)a3 + 20) > 7u )
        v15 = (_QWORD *)*v15;
      v19 = a3 + 58;
      if ( *((_QWORD *)a3 + 32) > 7u )
        v19 = (_QWORD *)*v19;
      ThrowWithFormatMessage(-1073221754, v19, *a3, v15, v18);
    }
    if ( v16 == -1073221753 )
    {
      v17 = a3 + 58;
      if ( *((_QWORD *)a3 + 32) > 7u )
        v17 = (_QWORD *)*v17;
      ThrowWithFormatMessage(-1073221753, v17, *a3);
    }
  }
  CheckForDuplicateLocalOpcode(a12, a3);
  v20 = (__int64)(*((_QWORD *)a3 + 38) - *((_QWORD *)a3 + 37)) >> 5;
  if ( v20 > 0x30 )
  {
    v21 = a3 + 58;
    if ( *((_QWORD *)a3 + 32) > 7u )
      v21 = (_QWORD *)*v21;
    ThrowWithFormatMessage(-1073221848, v21, *a3);
  }
  v22 = *((_QWORD *)a3 + 48);
  v23 = *((_QWORD *)a3 + 47);
  v24 = (v22 - v23) >> 3;
  if ( v20 < v24 )
  {
    v25 = v23 + 8 * v20;
LABEL_28:
    *((_QWORD *)a3 + 48) = v25;
    goto LABEL_29;
  }
  if ( v20 > v24 )
  {
    if ( v20 <= (*((_QWORD *)a3 + 49) - v23) >> 3 )
    {
      v26 = 8 * (v20 - v24);
      memset_0(*((void **)a3 + 48), 0, v26);
      v25 = v26 + v22;
      goto LABEL_28;
    }
    std::vector<KEYWORD_ENTRY *>::_Resize_reallocate<std::_Value_init_tag>(
      a3 + 94,
      (__int64)(*((_QWORD *)a3 + 38) - *((_QWORD *)a3 + 37)) >> 5);
  }
LABEL_29:
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    v28 = (EVENT_LIST *)(unsigned int)i;
    if ( (unsigned int)i >= v20 )
      break;
    v29 = 32LL * (unsigned int)i;
    KEYWORD_LIST::AddRef(a7, a2, v29 + *((_QWORD *)a3 + 37), a12, *((_QWORD *)a3 + 47) + 8 * i);
    v30 = (_QWORD *)(v29 + *((_QWORD *)a3 + 37));
    v31 = v30[2];
    if ( v30[3] > 7u )
      v30 = (_QWORD *)*v30;
    if ( (unsigned __int8)std::_Traits_equal<std::char_traits<wchar_t>>(v30, v31, L"win:EventlogClassic", 19) )
    {
      v32 = *((_QWORD *)a3 + 3) == 0;
      *((_BYTE *)a3 + 320) = 1;
      if ( !v32 || *((_QWORD *)a3 + 7) )
      {
        v33 = a3 + 58;
        if ( *((_QWORD *)a3 + 32) > 7u )
          v33 = (_QWORD *)*v33;
        ThrowWithFormatMessage(-1073221713, v33, *a3);
      }
    }
  }
  if ( *((_QWORD *)a3 + 11) )
  {
    CHANNEL_LIST::AddRef(a8, a2, (__int64)(a3 + 90));
    if ( !*(_DWORD *)(*((_QWORD *)a3 + 45) + 96LL) )
    {
      if ( !*((_QWORD *)a3 + 35) )
      {
        v34 = a3 + 58;
        if ( *((_QWORD *)a3 + 32) > 7u )
          v34 = (_QWORD *)*v34;
        ThrowWithFormatMessage(-1073221799, v34, *a3);
      }
      v35 = *((_QWORD *)a3 + 42);
      if ( !v35 || (unsigned __int8)(*(_BYTE *)(v35 + 32) - 1) > 3u )
      {
        v36 = a3 + 58;
        if ( *((_QWORD *)a3 + 32) > 7u )
          v36 = (_QWORD *)*v36;
        ThrowWithFormatMessage(-1073221798, v36, *a3);
      }
    }
  }
  if ( *((_QWORD *)a3 + 27) )
    TEMPLATE_LIST::AddRefFast(v28, a3 + 50, a11, a3 + 92);
  if ( *((_BYTE *)a3 + 320) )
  {
    *(_BYTE *)(a12 + 276) = 1;
    EVENT_LIST::ValidateLegacyCrimsonEvent(v28, (struct EVENT_ENTRY *)a3);
  }
  else if ( (*a3 & 0xFFFF0000) != 0 )
  {
    v37 = a3 + 58;
    if ( *((_QWORD *)a3 + 32) > 7u )
      v37 = (_QWORD *)*v37;
    ThrowWithFormatMessage(-1073221847, v37, *a3);
  }
}

```

## disassembly

```asm
0x18001ac70  push    rbx
0x18001ac72  push    rbp
0x18001ac73  push    rsi
0x18001ac74  push    rdi
0x18001ac75  push    r12
0x18001ac77  push    r14
0x18001ac79  push    r15
0x18001ac7b  sub     rsp, 30h
0x18001ac7f  mov     rbp, [rsp+68h+arg_58]
0x18001ac87  mov     rdi, r8
0x18001ac8a  add     r8, 68h ; 'h'
0x18001ac8e  mov     r10, r9
0x18001ac91  mov     r12, rdx
0x18001ac94  cmp     qword ptr [r8+10h], 0
0x18001ac99  jz      short loc_18001ACB2
0x18001ac9b  lea     rax, [rdi+150h]
0x18001aca2  mov     r9, rbp
0x18001aca5  mov     rcx, r10
0x18001aca8  mov     [rsp+68h+var_48], rax
0x18001acad  call    ?AddRef@LEVEL_LIST@@QEAAXAEBVWinMetaData@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAVETW_PROVIDER_ENTRY@@AEAPEAVLEVEL_ENTRY@@@Z; LEVEL_LIST::AddRef(WinMetaData const &,std::wstring const &,ETW_PROVIDER_ENTRY *,LEVEL_ENTRY * &)
0x18001acb2  lea     rsi, [rdi+0A8h]
0x18001acb9  cmp     qword ptr [rsi+10h], 0
0x18001acbe  lea     r14, [rdi+158h]
0x18001acc5  jz      short loc_18001ACEC
0x18001acc7  mov     r9, [rsp+68h+arg_48]
0x18001accf  mov     r8, rsi
0x18001acd2  mov     rcx, [rsp+68h+arg_20]
0x18001acda  mov     rdx, r12
0x18001acdd  mov     [rsp+68h+var_40], r14
0x18001ace2  mov     [rsp+68h+var_48], rbp
0x18001ace7  call    ?AddRefFast@TASK_LIST@@QEBAXAEBVWinMetaData@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAUTASK_ENTRY_MAP@1@PEAVETW_PROVIDER_ENTRY@@AEAPEAVTASK_ENTRY@@@Z; TASK_LIST::AddRefFast(WinMetaData const &,std::wstring const &,TASK_LIST::TASK_ENTRY_MAP &,ETW_PROVIDER_ENTRY *,TASK_ENTRY * &)
0x18001acec  lea     rbx, [rdi+88h]
0x18001acf3  cmp     qword ptr [rbx+10h], 0
0x18001acf8  jz      loc_18001ADDB
0x18001acfe  mov     rax, [r14]
0x18001ad01  lea     r15, [rdi+160h]
0x18001ad08  mov     rcx, [rsp+68h+arg_28]
0x18001ad10  mov     r9, rbp
0x18001ad13  mov     [rsp+68h+var_40], rax
0x18001ad18  mov     r8, rbx
0x18001ad1b  mov     rdx, r12
0x18001ad1e  mov     [rsp+68h+var_48], r15
0x18001ad23  call    ?AddRef@OPCODE_LIST@@QEAAJAEBVWinMetaData@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAVETW_PROVIDER_ENTRY@@AEAPEBVOPCODE_ENTRY@@PEAVTASK_ENTRY@@@Z; OPCODE_LIST::AddRef(WinMetaData const &,std::wstring const &,ETW_PROVIDER_ENTRY *,OPCODE_ENTRY const * &,TASK_ENTRY *)
0x18001ad28  mov     r10d, 0C007EF86h
0x18001ad2e  cmp     eax, r10d
0x18001ad31  jz      short loc_18001AD98
0x18001ad33  mov     r10d, 0C007EF87h
0x18001ad39  cmp     eax, r10d
0x18001ad3c  jnz     loc_18001ADDB
0x18001ad42  cmp     qword ptr [rsi+18h], 7
0x18001ad47  jbe     short loc_18001AD4C
0x18001ad49  mov     rsi, [rsi]
0x18001ad4c  mov     rax, [r15]
0x18001ad4f  mov     rcx, [rax+80h]
0x18001ad56  cmp     qword ptr [rcx+18h], 7
0x18001ad5b  jbe     short loc_18001AD60
0x18001ad5d  mov     rcx, [rcx]
0x18001ad60  lea     r9, [rdi+88h]
0x18001ad67  cmp     qword ptr [r9+18h], 7
0x18001ad6c  jbe     short loc_18001AD71
0x18001ad6e  mov     r9, [r9]
0x18001ad71  lea     rdx, [rdi+0E8h]
0x18001ad78  cmp     qword ptr [rdx+18h], 7
0x18001ad7d  jbe     short loc_18001AD82
0x18001ad7f  mov     rdx, [rdx]
0x18001ad82  mov     r8d, [rdi]
0x18001ad85  mov     [rsp+68h+var_40], rsi
0x18001ad8a  mov     [rsp+68h+var_48], rcx
0x18001ad8f  mov     ecx, r10d; int
0x18001ad92  call    ?ThrowWithFormatMessage@@YAXJZZ; ThrowWithFormatMessage(long,...)
0x18001ad98  mov     rax, [r15]
0x18001ad9b  mov     rcx, [rax+80h]
0x18001ada2  cmp     qword ptr [rcx+18h], 7
0x18001ada7  jbe     short loc_18001ADAC
0x18001ada9  mov     rcx, [rcx]
0x18001adac  cmp     qword ptr [rbx+18h], 7
0x18001adb1  jbe     short loc_18001ADB6
0x18001adb3  mov     rbx, [rbx]
0x18001adb6  lea     rdx, [rdi+0E8h]
0x18001adbd  cmp     qword ptr [rdx+18h], 7
0x18001adc2  jbe     short loc_18001ADC7
0x18001adc4  mov     rdx, [rdx]
0x18001adc7  mov     r8d, [rdi]
0x18001adca  mov     r9, rbx
0x18001adcd  mov     [rsp+68h+var_48], rcx
0x18001add2  mov     ecx, r10d; int
0x18001add5  call    ?ThrowWithFormatMessage@@YAXJZZ; ThrowWithFormatMessage(long,...)
0x18001addb  mov     rdx, rdi
0x18001adde  mov     rcx, rbp
0x18001ade1  call    CheckForDuplicateLocalOpcode
0x18001ade6  mov     rsi, [rdi+130h]
0x18001aded  sub     rsi, [rdi+128h]
0x18001adf4  sar     rsi, 5
0x18001adf8  cmp     rsi, 30h ; '0'
0x18001adfc  jbe     short loc_18001AE1D
0x18001adfe  lea     rdx, [rdi+0E8h]
0x18001ae05  cmp     qword ptr [rdx+18h], 7
0x18001ae0a  jbe     short loc_18001AE0F
0x18001ae0c  mov     rdx, [rdx]
0x18001ae0f  mov     r8d, [rdi]
0x18001ae12  mov     ecx, 0C007EF28h; int
0x18001ae17  call    ?ThrowWithFormatMessage@@YAXJZZ; ThrowWithFormatMessage(long,...)
0x18001ae1d  lea     r14, [rdi+178h]
0x18001ae24  mov     r15, [r14+8]
0x18001ae28  mov     rdx, [r14]
0x18001ae2b  mov     rcx, r15
0x18001ae2e  sub     rcx, rdx
0x18001ae31  sar     rcx, 3
0x18001ae35  cmp     rsi, rcx
0x18001ae38  jnb     short loc_18001AE40
0x18001ae3a  lea     rax, [rdx+rsi*8]
0x18001ae3e  jmp     short loc_18001AE7E
0x18001ae40  jbe     short loc_18001AE82
0x18001ae42  mov     rax, [r14+10h]
0x18001ae46  sub     rax, rdx
0x18001ae49  sar     rax, 3
0x18001ae4d  cmp     rsi, rax
0x18001ae50  jbe     short loc_18001AE5F
0x18001ae52  mov     rdx, rsi
0x18001ae55  mov     rcx, r14
0x18001ae58  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@PEAVKEYWORD_ENTRY@@V?$allocator@PEAVKEYWORD_ENTRY@@@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<KEYWORD_ENTRY *>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18001ae5d  jmp     short loc_18001AE82
0x18001ae5f  mov     rax, rsi
0x18001ae62  xor     edx, edx; Val
0x18001ae64  sub     rax, rcx
0x18001ae67  mov     rcx, r15; void *
0x18001ae6a  lea     rbx, ds:0[rax*8]
0x18001ae72  mov     r8, rbx; Size
0x18001ae75  call    memset_0
0x18001ae7a  lea     rax, [rbx+r15]
0x18001ae7e  mov     [r14+8], rax
0x18001ae82  xor     r14d, r14d
0x18001ae85  mov     ecx, r14d
0x18001ae88  cmp     rcx, rsi
0x18001ae8b  jnb     loc_18001AF2E
0x18001ae91  mov     rax, [rdi+178h]
0x18001ae98  mov     ebx, ecx
0x18001ae9a  mov     r8, [rdi+128h]
0x18001aea1  mov     r9, rbp
0x18001aea4  shl     rbx, 5
0x18001aea8  mov     rdx, r12
0x18001aeab  add     r8, rbx
0x18001aeae  lea     rcx, [rax+r14*8]
0x18001aeb2  mov     [rsp+68h+var_48], rcx
0x18001aeb7  mov     rcx, [rsp+68h+arg_30]
0x18001aebf  call    ?AddRef@KEYWORD_LIST@@QEAAXAEBVWinMetaData@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAVETW_PROVIDER_ENTRY@@AEAPEAVKEYWORD_ENTRY@@@Z; KEYWORD_LIST::AddRef(WinMetaData const &,std::wstring const &,ETW_PROVIDER_ENTRY *,KEYWORD_ENTRY * &)
0x18001aec4  mov     rcx, [rdi+128h]
0x18001aecb  add     rcx, rbx
0x18001aece  cmp     qword ptr [rcx+18h], 7
0x18001aed3  mov     rdx, [rcx+10h]
0x18001aed7  jbe     short loc_18001AEDC
0x18001aed9  mov     rcx, [rcx]
0x18001aedc  mov     r9d, 13h
0x18001aee2  lea     r8, aWinEventlogcla; "win:EventlogClassic"
0x18001aee9  call    ??$_Traits_equal@U?$char_traits@_W@std@@@std@@YA_NQEB_W_K01@Z; std::_Traits_equal<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x18001aeee  test    al, al
0x18001aef0  jz      short loc_18001AF07
0x18001aef2  cmp     qword ptr [rdi+18h], 0
0x18001aef7  mov     byte ptr [rdi+140h], 1
0x18001aefe  jnz     short loc_18001AF0F
0x18001af00  cmp     qword ptr [rdi+38h], 0
0x18001af05  jnz     short loc_18001AF0F
0x18001af07  inc     r14d
0x18001af0a  jmp     loc_18001AE85
0x18001af0f  lea     rdx, [rdi+0E8h]
0x18001af16  cmp     qword ptr [rdx+18h], 7
0x18001af1b  jbe     short loc_18001AF20
0x18001af1d  mov     rdx, [rdx]
0x18001af20  mov     r8d, [rdi]
0x18001af23  mov     ecx, 0C007EFAFh; int
0x18001af28  call    ?ThrowWithFormatMessage@@YAXJZZ; ThrowWithFormatMessage(long,...)
0x18001af2e  lea     r8, [rdi+48h]
0x18001af32  cmp     qword ptr [r8+10h], 0
0x18001af37  jz      loc_18001AFC2
0x18001af3d  mov     rcx, [rsp+68h+arg_38]; this
0x18001af45  lea     rbx, [rdi+168h]
0x18001af4c  mov     r9, rbp
0x18001af4f  mov     [rsp+68h+var_48], rbx; __int64
0x18001af54  mov     rdx, r12; struct WinMetaData *
0x18001af57  call    ?AddRef@CHANNEL_LIST@@QEAAXAEBVWinMetaData@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAVETW_PROVIDER_ENTRY@@AEAPEAVCHANNEL_ENTRY@@@Z; CHANNEL_LIST::AddRef(WinMetaData const &,std::wstring const &,ETW_PROVIDER_ENTRY *,CHANNEL_ENTRY * &)
0x18001af5c  mov     rax, [rbx]
0x18001af5f  cmp     dword ptr [rax+60h], 0
0x18001af63  jnz     short loc_18001AFC2
0x18001af65  cmp     qword ptr [rdi+118h], 0
0x18001af6d  jnz     short loc_18001AF8E
0x18001af6f  lea     rdx, [rdi+0E8h]
0x18001af76  cmp     qword ptr [rdx+18h], 7
0x18001af7b  jbe     short loc_18001AF80
0x18001af7d  mov     rdx, [rdx]
0x18001af80  mov     r8d, [rdi]
0x18001af83  mov     ecx, 0C007EF59h; int
0x18001af88  call    ?ThrowWithFormatMessage@@YAXJZZ; ThrowWithFormatMessage(long,...)
0x18001af8e  mov     rax, [rdi+150h]
0x18001af95  test    rax, rax
0x18001af98  jz      short loc_18001AFA3
0x18001af9a  mov     al, [rax+20h]
0x18001af9d  dec     al
0x18001af9f  cmp     al, 3
0x18001afa1  jbe     short loc_18001AFC2
0x18001afa3  lea     rdx, [rdi+0E8h]
0x18001afaa  cmp     qword ptr [rdx+18h], 7
0x18001afaf  jbe     short loc_18001AFB4
0x18001afb1  mov     rdx, [rdx]
0x18001afb4  mov     r8d, [rdi]
0x18001afb7  mov     ecx, 0C007EF5Ah; int
0x18001afbc  call    ?ThrowWithFormatMessage@@YAXJZZ; ThrowWithFormatMessage(long,...)
0x18001afc2  lea     rdx, [rdi+0C8h]
0x18001afc9  cmp     qword ptr [rdx+10h], 0
0x18001afce  jz      short loc_18001AFE4
0x18001afd0  mov     r8, [rsp+68h+arg_50]
0x18001afd8  lea     r9, [rdi+170h]
0x18001afdf  call    ?AddRefFast@TEMPLATE_LIST@@QEBAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$map@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@PEAVTEMPLATE_ENTRY@@U?$less@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@PEAVTEMPLATE_ENTRY@@@std@@@2@@3@AEAPEAVTEMPLATE_ENTRY@@@Z; TEMPLATE_LIST::AddRefFast(std::wstring const &,std::map<std::wstring_view,TEMPLATE_ENTRY *> const &,TEMPLATE_ENTRY * &)
0x18001afe4  cmp     byte ptr [rdi+140h], 0
0x18001afeb  jz      short loc_18001B00B
0x18001afed  mov     rdx, rdi; struct EVENT_ENTRY *
0x18001aff0  mov     byte ptr [rbp+114h], 1
0x18001aff7  call    ?ValidateLegacyCrimsonEvent@EVENT_LIST@@AEAAXPEAVEVENT_ENTRY@@@Z; EVENT_LIST::ValidateLegacyCrimsonEvent(EVENT_ENTRY *)
0x18001affc  add     rsp, 30h
0x18001b000  pop     r15
0x18001b002  pop     r14
0x18001b004  pop     r12
0x18001b006  pop     rdi
0x18001b007  pop     rsi
0x18001b008  pop     rbp
0x18001b009  pop     rbx
0x18001b00a  retn
0x18001b00b  test    dword ptr [rdi], 0FFFF0000h
0x18001b011  jz      short loc_18001AFFC
0x18001b013  lea     rdx, [rdi+0E8h]
0x18001b01a  cmp     qword ptr [rdx+18h], 7
0x18001b01f  jbe     short loc_18001B024
0x18001b021  mov     rdx, [rdx]
0x18001b024  mov     r8d, [rdi]
0x18001b027  mov     ecx, 0C007EF29h; int
0x18001b02c  call    ?ThrowWithFormatMessage@@YAXJZZ; ThrowWithFormatMessage(long,...)
```
