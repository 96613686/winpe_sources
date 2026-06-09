# CTriggerMonitor::ProcessMessageFromAdminQueue(CMsgProperties const *)

- ea: `0x140009994`
- end: `0x140009b62`
- name: `?ProcessMessageFromAdminQueue@CTriggerMonitor@@AEAAJPEBVCMsgProperties@@@Z`
- size: `462`
- prototype: `__int64 __fastcall(CTriggerMonitorPool **this, const struct CMsgProperties *)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400098f4`

## callees

- `0x1400031a0`
- `0x140003378`
- `0x140003868`
- `0x140007a18`
- `0x140009994`
- `0x14000aee8`
- `0x14000ec24`
- `0x14000ed18`

## import_xrefs

- `msvcrt!wcsstr` at `0x140009a4a`
- `msvcrt!wcsstr` at `0x140009a75`
- `msvcrt!wcsstr` at `0x140009a9d`
- `msvcrt!wcsstr` at `0x140009ac2`
- `msvcrt!wcsstr` at `0x140009ae4`
- `msvcrt!wcsstr` at `0x140009b09`
- `msvcrt!wcsstr` at `0x140009a4a`
- `msvcrt!wcsstr` at `0x140009a75`
- `msvcrt!wcsstr` at `0x140009a9d`
- `msvcrt!wcsstr` at `0x140009ac2`
- `msvcrt!wcsstr` at `0x140009ae4`
- `msvcrt!wcsstr` at `0x140009b09`
- `OLEAUT32!__imp_VariantInit` at `0x1400099dd`
- `OLEAUT32!__imp_VariantInit` at `0x1400099dd`
- `OLEAUT32!__imp_VariantChangeType` at `0x140009a00`
- `OLEAUT32!__imp_VariantChangeType` at `0x140009a00`

## string_xrefs

- `0x140009a43`: `MSMQTriggerNotification:TriggerUpdated`
- `0x140009a96`: `MSMQTriggerNotification:TriggerDeleted`
- `0x140009abb`: `MSMQTriggerNotification:RuleUpdated`
- `0x140009b02`: `MSMQTriggerNotification:RuleDeleted`

## pseudocode

```c
__int64 __fastcall CTriggerMonitor::ProcessMessageFromAdminQueue(
        CTriggerMonitorPool **this,
        const struct CMsgProperties *a2)
{
  __int64 Label; // rax
  VARIANTARG *v4; // rbx
  HRESULT v5; // eax
  const wchar_t **v6; // rbx
  const wchar_t *v7; // rcx
  int v8; // ebx
  const wchar_t *v9; // rcx
  const wchar_t *v10; // rcx
  const wchar_t *v11; // rcx
  const wchar_t *v12; // rcx
  const wchar_t *v13; // rcx
  struct CAdminMessage *v14; // rax
  unsigned int v15; // ebx
  VARIANTARG pvarg; // [rsp+20h] [rbp-30h] BYREF
  VARIANTARG v18; // [rsp+38h] [rbp-18h] BYREF
  const wchar_t **v19; // [rsp+80h] [rbp+30h] BYREF
  struct CAdminMessage *v20; // [rsp+88h] [rbp+38h]

  v19 = 0;
  Label = CMsgProperties::GetLabel(a2, &v18);
  v4 = (VARIANTARG *)Label;
  if ( *(_WORD *)Label == 8 )
  {
    _bstr_t::operator=((_bstr_t *)&v19, *(const wchar_t **)(Label + 8));
  }
  else
  {
    VariantInit(&pvarg);
    if ( &pvarg != v4 || pvarg.vt != 8 )
    {
      v5 = VariantChangeType(&pvarg, v4, 0, 8u);
      if ( v5 < 0 )
        _com_issue_error(v5);
    }
    _bstr_t::operator=((_bstr_t *)&v19, pvarg.bstrVal);
    _variant_t::~_variant_t(&pvarg);
  }
  _variant_t::~_variant_t(&v18);
  v6 = v19;
  if ( v19 )
    v7 = *v19;
  else
    v7 = 0;
  if ( wcsstr(v7, L"MSMQTriggerNotification:TriggerUpdated") )
  {
    v8 = 1;
  }
  else
  {
    if ( v6 )
      v9 = *v6;
    else
      v9 = 0;
    if ( wcsstr(v9, L"MSMQTriggerNotification:TriggerAdded") )
    {
      v8 = 3;
    }
    else
    {
      if ( v6 )
        v10 = *v6;
      else
        v10 = 0;
      if ( wcsstr(v10, L"MSMQTriggerNotification:TriggerDeleted") )
      {
        v8 = 2;
      }
      else
      {
        if ( v6 )
          v11 = *v6;
        else
          v11 = 0;
        if ( wcsstr(v11, L"MSMQTriggerNotification:RuleUpdated") )
        {
          v8 = 4;
        }
        else
        {
          if ( v6 )
            v12 = *v6;
          else
            v12 = 0;
          if ( wcsstr(v12, L"MSMQTriggerNotification:RuleAdded") )
          {
            v8 = 6;
          }
          else
          {
            if ( v6 )
              v13 = *v6;
            else
              v13 = 0;
            if ( !wcsstr(v13, L"MSMQTriggerNotification:RuleDeleted") )
            {
              _bstr_t::_Free((_bstr_t *)&v19);
              return 2147500037LL;
            }
            v8 = 5;
          }
        }
      }
    }
  }
  v14 = (struct CAdminMessage *)MmAllocate(4u);
  v20 = v14;
  if ( v14 )
    *(_DWORD *)v14 = v8;
  v15 = CTriggerMonitorPool::AcceptAdminMessage(this[13], v14);
  _bstr_t::_Free((_bstr_t *)&v19);
  return v15;
}

```

## disassembly

```asm
0x140009994  mov     [rsp-18h+arg_0], rbx
0x140009999  push    rbp
0x14000999a  push    rsi
0x14000999b  push    rdi
0x14000999c  mov     rbp, rsp
0x14000999f  sub     rsp, 50h
0x1400099a3  mov     rax, rdx
0x1400099a6  mov     rdi, rcx
0x1400099a9  mov     [rbp+arg_10], 0
0x1400099b1  lea     rdx, [rbp+var_18]
0x1400099b5  mov     rcx, rax
0x1400099b8  call    ?GetLabel@CMsgProperties@@QEBA?AV_variant_t@@XZ; CMsgProperties::GetLabel(void)
0x1400099bd  mov     rbx, rax
0x1400099c0  mov     esi, 8
0x1400099c5  cmp     [rax], si
0x1400099c8  jnz     short loc_1400099D9
0x1400099ca  mov     rdx, [rax+8]
0x1400099ce  lea     rcx, [rbp+arg_10]
0x1400099d2  call    ??4_bstr_t@@QEAAAEAV0@PEB_W@Z; _bstr_t::operator=(wchar_t const *)
0x1400099d7  jmp     short loc_140009A2A
0x1400099d9  lea     rcx, [rbp+pvarg]; pvarg
0x1400099dd  call    cs:__imp_VariantInit
0x1400099e3  nop
0x1400099e4  lea     rax, [rbp+pvarg]
0x1400099e8  cmp     rax, rbx
0x1400099eb  jnz     short loc_1400099F3
0x1400099ed  cmp     si, word ptr [rbp+pvarg]
0x1400099f1  jz      short loc_140009A12
0x1400099f3  mov     r9d, esi; vt
0x1400099f6  xor     r8d, r8d; wFlags
0x1400099f9  mov     rdx, rbx; pvarSrc
0x1400099fc  lea     rcx, [rbp+pvarg]; pvargDest
0x140009a00  call    cs:__imp_VariantChangeType
0x140009a06  test    eax, eax
0x140009a08  jns     short loc_140009A12
0x140009a0a  mov     ecx, eax; int
0x140009a0c  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x140009a12  mov     rdx, qword ptr [rbp+pvarg+8]
0x140009a16  lea     rcx, [rbp+arg_10]
0x140009a1a  call    ??4_bstr_t@@QEAAAEAV0@PEB_W@Z; _bstr_t::operator=(wchar_t const *)
0x140009a1f  nop
0x140009a20  lea     rcx, [rbp+pvarg]; this
0x140009a24  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x140009a29  nop
0x140009a2a  lea     rcx, [rbp+var_18]; this
0x140009a2e  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x140009a33  mov     rbx, [rbp+arg_10]
0x140009a37  test    rbx, rbx
0x140009a3a  jz      short loc_140009A41
0x140009a3c  mov     rcx, [rbx]
0x140009a3f  jmp     short loc_140009A43
0x140009a41  xor     ecx, ecx; Str
0x140009a43  lea     rdx, aMsmqtriggernot; "MSMQTriggerNotification:TriggerUpdated"
0x140009a4a  call    cs:__imp_wcsstr
0x140009a50  mov     esi, 4
0x140009a55  test    rax, rax
0x140009a58  jz      short loc_140009A62
0x140009a5a  lea     ebx, [rsi-3]
0x140009a5d  jmp     loc_140009B19
0x140009a62  test    rbx, rbx
0x140009a65  jz      short loc_140009A6C
0x140009a67  mov     rcx, [rbx]
0x140009a6a  jmp     short loc_140009A6E
0x140009a6c  xor     ecx, ecx; Str
0x140009a6e  lea     rdx, aMsmqtriggernot_3; "MSMQTriggerNotification:TriggerAdded"
0x140009a75  call    cs:__imp_wcsstr
0x140009a7b  test    rax, rax
0x140009a7e  jz      short loc_140009A8A
0x140009a80  mov     ebx, 3
0x140009a85  jmp     loc_140009B19
0x140009a8a  test    rbx, rbx
0x140009a8d  jz      short loc_140009A94
0x140009a8f  mov     rcx, [rbx]
0x140009a92  jmp     short loc_140009A96
0x140009a94  xor     ecx, ecx; Str
0x140009a96  lea     rdx, aMsmqtriggernot_4; "MSMQTriggerNotification:TriggerDeleted"
0x140009a9d  call    cs:__imp_wcsstr
0x140009aa3  test    rax, rax
0x140009aa6  jz      short loc_140009AAF
0x140009aa8  mov     ebx, 2
0x140009aad  jmp     short loc_140009B19
0x140009aaf  test    rbx, rbx
0x140009ab2  jz      short loc_140009AB9
0x140009ab4  mov     rcx, [rbx]
0x140009ab7  jmp     short loc_140009ABB
0x140009ab9  xor     ecx, ecx; Str
0x140009abb  lea     rdx, aMsmqtriggernot_2; "MSMQTriggerNotification:RuleUpdated"
0x140009ac2  call    cs:__imp_wcsstr
0x140009ac8  test    rax, rax
0x140009acb  jz      short loc_140009AD1
0x140009acd  mov     ebx, esi
0x140009acf  jmp     short loc_140009B19
0x140009ad1  test    rbx, rbx
0x140009ad4  jz      short loc_140009ADB
0x140009ad6  mov     rcx, [rbx]
0x140009ad9  jmp     short loc_140009ADD
0x140009adb  xor     ecx, ecx; Str
0x140009add  lea     rdx, aMsmqtriggernot_1; "MSMQTriggerNotification:RuleAdded"
0x140009ae4  call    cs:__imp_wcsstr
0x140009aea  test    rax, rax
0x140009aed  jz      short loc_140009AF6
0x140009aef  mov     ebx, 6
0x140009af4  jmp     short loc_140009B19
0x140009af6  test    rbx, rbx
0x140009af9  jz      short loc_140009B00
0x140009afb  mov     rcx, [rbx]
0x140009afe  jmp     short loc_140009B02
0x140009b00  xor     ecx, ecx; Str
0x140009b02  lea     rdx, aMsmqtriggernot_0; "MSMQTriggerNotification:RuleDeleted"
0x140009b09  call    cs:__imp_wcsstr
0x140009b0f  test    rax, rax
0x140009b12  jz      short loc_140009B47
0x140009b14  mov     ebx, 5
0x140009b19  mov     rcx, rsi; unsigned __int64
0x140009b1c  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x140009b21  mov     [rbp+arg_18], rax
0x140009b25  test    rax, rax
0x140009b28  jz      short loc_140009B2C
0x140009b2a  mov     [rax], ebx
0x140009b2c  mov     rdx, rax; struct CAdminMessage *
0x140009b2f  mov     rcx, [rdi+68h]; this
0x140009b33  call    ?AcceptAdminMessage@CTriggerMonitorPool@@AEAAJPEAVCAdminMessage@@@Z; CTriggerMonitorPool::AcceptAdminMessage(CAdminMessage *)
0x140009b38  mov     ebx, eax
0x140009b3a  lea     rcx, [rbp+arg_10]; this
0x140009b3e  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x140009b43  mov     eax, ebx
0x140009b45  jmp     short loc_140009B55
0x140009b47  lea     rcx, [rbp+arg_10]; this
0x140009b4b  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x140009b50  mov     eax, 80004005h
0x140009b55  mov     rbx, [rsp+50h+arg_0]
0x140009b5a  add     rsp, 50h
0x140009b5e  pop     rdi
0x140009b5f  pop     rsi
0x140009b60  pop     rbp
0x140009b61  retn
```
