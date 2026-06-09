# RegistryConfig::ParseCommandSet(HKEY__ *,ushort const *)

- ea: `0x140008f54`
- end: `0x1400090e6`
- name: `?ParseCommandSet@RegistryConfig@@AEAA?AUCommandSet@@PEAUHKEY__@@PEBG@Z`
- size: `402`
- prototype: `__int64 __fastcall(__int64, __int64, HKEY, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400090ec`

## callees

- `0x1400011ac`
- `0x140001518`
- `0x140007d20`
- `0x140007e3c`
- `0x140008f54`
- `0x14000972c`
- `0x140009c08`
- `0x14000a370`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140008ff9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140008ff9`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall RegistryConfig::ParseCommandSet(__int64 a1, __int64 a2, HKEY a3, int *a4)
{
  __int64 v8; // rsi
  int v9; // r8d
  int v10; // r9d
  __int64 v11; // rcx
  int v12; // ecx
  DWORD pcbData[3]; // [rsp+44h] [rbp-55h] BYREF
  _QWORD v15[4]; // [rsp+50h] [rbp-49h] BYREF
  _BYTE v16[32]; // [rsp+70h] [rbp-29h] BYREF
  int *v17; // [rsp+90h] [rbp-9h]
  int v18; // [rsp+98h] [rbp-1h]
  int v19; // [rsp+9Ch] [rbp+3h]
  _QWORD *v20; // [rsp+A0h] [rbp+7h]
  __int64 v21; // [rsp+A8h] [rbp+Fh]

  v15[2] = a2;
  *(_DWORD *)a2 = 0;
  v8 = a2 + 8;
  *(_QWORD *)(a2 + 8) = 0;
  *(_QWORD *)(a2 + 16) = 0;
  *(_QWORD *)(a2 + 8) = std::_List_alloc<0,std::_List_base_types<Command>>::_Buynode0(a1, 0, 0);
  *(_QWORD *)(a2 + 48) = 7;
  *(_QWORD *)(a2 + 40) = 0;
  *(_WORD *)(a2 + 24) = 0;
  std::wstring::assign((void *)(a2 + 24), a4);
  pcbData[0] = 4;
  if ( RegGetValueW(a3, 0, L"altitude", 0x10u, 0, (PVOID)a2, pcbData) )
  {
    if ( (unsigned int)dword_140010000 > 2 )
    {
      v15[0] = a4;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        2,
        (unsigned int)byte_14000D7CB,
        v9,
        v10,
        (__int64)v15);
    }
  }
  else
  {
    if ( (unsigned int)dword_140010000 > 4 )
    {
      LODWORD(v15[0]) = *(_DWORD *)a2;
      v20 = v15;
      v21 = 4;
      if ( a4 )
      {
        v11 = -1;
        do
          ++v11;
        while ( *((_WORD *)a4 + v11) );
        v12 = 2 * v11 + 2;
      }
      else
      {
        a4 = &dword_14000C834;
        v12 = 2;
      }
      v17 = a4;
      v18 = v12;
      v19 = 0;
      tlgWriteTransfer_EventWriteTransfer(&dword_140010000, byte_14000D783, 0, 0, 4, v16);
    }
    v15[0] = a2;
    v15[1] = a1;
    ForEachRegSubKey__lambda_b2932f37bd01d37ef5d2c59b4ad9c5b6_(a3);
  }
  std::list<Command>::sort(v8);
  return a2;
}

```

## disassembly

```asm
0x140008f54  push    rbp
0x140008f56  push    rbx
0x140008f57  push    rsi
0x140008f58  push    rdi
0x140008f59  push    r12
0x140008f5b  push    r14
0x140008f5d  push    r15
0x140008f5f  lea     rbp, [rsp-27h]
0x140008f64  sub     rsp, 0C0h
0x140008f6b  mov     rax, cs:__security_cookie
0x140008f72  xor     rax, rsp
0x140008f75  mov     [rbp+57h+var_40], rax
0x140008f79  mov     rbx, r9
0x140008f7c  mov     r14, r8
0x140008f7f  mov     rdi, rdx
0x140008f82  mov     r15, rcx
0x140008f85  mov     [rbp+57h+var_90], rdx
0x140008f89  xor     r12d, r12d
0x140008f8c  mov     [rbp+57h+var_B0], r12d
0x140008f90  mov     [rdx], r12d
0x140008f93  lea     rsi, [rdx+8]
0x140008f97  mov     [rsi], r12
0x140008f9a  mov     [rsi+8], r12
0x140008f9e  xor     r8d, r8d
0x140008fa1  xor     edx, edx
0x140008fa3  call    ?_Buynode0@?$_List_alloc@$0A@U?$_List_base_types@UCommand@@V?$allocator@UCommand@@@std@@@std@@@std@@QEAAPEAU?$_List_node@UCommand@@PEAX@2@PEAU32@0@Z; std::_List_alloc<0,std::_List_base_types<Command>>::_Buynode0(std::_List_node<Command,void *> *,std::_List_node<Command,void *> *)
0x140008fa8  mov     [rsi], rax
0x140008fab  lea     rcx, [rdi+18h]; void *
0x140008faf  mov     qword ptr [rcx+18h], 7
0x140008fb7  mov     [rcx+10h], r12
0x140008fbb  mov     [rcx], r12w
0x140008fbf  mov     [rbp+57h+var_B0], 1
0x140008fc6  mov     rdx, rbx; Src
0x140008fc9  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x140008fce  mov     [rbp+57h+var_AC], 4
0x140008fd5  lea     rax, [rbp+57h+var_AC]
0x140008fd9  mov     [rsp+0F0h+pcbData], rax; pcbData
0x140008fde  mov     [rsp+0F0h+pvData], rdi; pvData
0x140008fe3  mov     [rsp+0F0h+pdwType], r12; pdwType
0x140008fe8  lea     r9d, [r12+10h]; dwFlags
0x140008fed  lea     r8, Value; "altitude"
0x140008ff4  xor     edx, edx; lpSubKey
0x140008ff6  mov     rcx, r14; hkey
0x140008ff9  call    cs:__imp_RegGetValueW
0x140008fff  test    eax, eax
0x140009001  mov     eax, cs:dword_140010000
0x140009007  jnz     loc_14000909A
0x14000900d  cmp     eax, 4
0x140009010  jbe     short loc_140009084
0x140009012  mov     eax, [rdi]
0x140009014  mov     dword ptr [rbp+57h+var_A0], eax
0x140009017  lea     rax, [rbp+57h+var_A0]
0x14000901b  mov     [rbp+57h+var_50], rax
0x14000901f  mov     [rbp+57h+var_48], 4
0x140009027  test    rbx, rbx
0x14000902a  jz      short loc_140009043
0x14000902c  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140009030  inc     rcx
0x140009033  cmp     [rbx+rcx*2], r12w
0x140009038  jnz     short loc_140009030
0x14000903a  lea     ecx, ds:2[rcx*2]
0x140009041  jmp     short loc_14000904F
0x140009043  lea     rbx, dword_14000C834
0x14000904a  mov     ecx, 2
0x14000904f  mov     [rbp+57h+var_60], rbx
0x140009053  mov     [rbp+57h+var_58], ecx
0x140009056  mov     [rbp+57h+var_54], r12d
0x14000905a  lea     rax, [rbp+57h+var_80]
0x14000905e  mov     [rsp+0F0h+pvData], rax
0x140009063  mov     dword ptr [rsp+0F0h+pdwType], 4
0x14000906b  xor     r9d, r9d
0x14000906e  xor     r8d, r8d
0x140009071  lea     rdx, byte_14000D783
0x140009078  lea     rcx, dword_140010000
0x14000907f  call    _tlgWriteTransfer_EventWriteTransfer
0x140009084  mov     [rbp+57h+var_A0], rdi
0x140009088  mov     [rbp+57h+var_98], r15
0x14000908c  lea     rdx, [rbp+57h+var_A0]
0x140009090  mov     rcx, r14; hKey
0x140009093  call    ForEachRegSubKey__lambda_b2932f37bd01d37ef5d2c59b4ad9c5b6___; ForEachRegSubKey__lambda_b2932f37bd01d37ef5d2c59b4ad9c5b6_
0x140009098  jmp     short loc_1400090BC
0x14000909a  mov     ecx, 2
0x14000909f  cmp     eax, ecx
0x1400090a1  jbe     short loc_1400090BC
0x1400090a3  mov     [rbp+57h+var_A0], rbx
0x1400090a7  lea     rax, [rbp+57h+var_A0]
0x1400090ab  mov     [rsp+0F0h+pdwType], rax
0x1400090b0  lea     rdx, byte_14000D7CB
0x1400090b7  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x1400090bc  mov     rcx, rsi
0x1400090bf  call    ?sort@?$list@UCommand@@V?$allocator@UCommand@@@std@@@std@@QEAAXXZ; std::list<Command>::sort(void)
0x1400090c4  mov     rax, rdi
0x1400090c7  mov     rcx, [rbp+57h+var_40]
0x1400090cb  xor     rcx, rsp; StackCookie
0x1400090ce  call    __security_check_cookie
0x1400090d3  add     rsp, 0C0h
0x1400090da  pop     r15
0x1400090dc  pop     r14
0x1400090de  pop     r12
0x1400090e0  pop     rdi
0x1400090e1  pop     rsi
0x1400090e2  pop     rbx
0x1400090e3  pop     rbp
0x1400090e4  retn
```
