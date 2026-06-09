# RegistryConfig::ParseCommandSet(HKEY__ *,ushort const *)

- ea: `0x18000b660`
- end: `0x18000b7d5`
- name: `?ParseCommandSet@RegistryConfig@@AEAA?AUCommandSet@@PEAUHKEY__@@PEBG@Z`
- size: `373`
- prototype: `void **__fastcall(__int64, void **, HKEY, char *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000b7dc`

## callees

- `0x18000108c`
- `0x180001340`
- `0x180007c18`
- `0x180009f34`
- `0x18000a0dc`
- `0x18000b660`
- `0x18000be80`
- `0x18000c600`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000b6e2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000b6e2`

## pseudocode

```c
void **__fastcall RegistryConfig::ParseCommandSet(__int64 a1, void **a2, HKEY a3, char *a4)
{
  __int64 v8; // r8
  __int64 v9; // r9
  __int64 v10; // rcx
  int v11; // ecx
  DWORD pcbData[3]; // [rsp+44h] [rbp-45h] BYREF
  _QWORD v14[9]; // [rsp+50h] [rbp-39h] BYREF
  int v15; // [rsp+98h] [rbp+Fh]
  int v16; // [rsp+9Ch] [rbp+13h]
  _QWORD *v17; // [rsp+A0h] [rbp+17h]
  __int64 v18; // [rsp+A8h] [rbp+1Fh]

  v14[2] = a2;
  CommandSet::CommandSet((CommandSet *)a2);
  std::wstring::assign(a2 + 3, a4);
  pcbData[0] = 4;
  if ( RegGetValueW(a3, 0, L"altitude", 0x10u, 0, a2, pcbData) )
  {
    if ( (unsigned int)dword_180014230 > 2 )
    {
      v14[0] = a4;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        2,
        (__int64)byte_180010D8B,
        v8,
        v9,
        v14);
    }
  }
  else
  {
    if ( (unsigned int)dword_180014230 > 4 )
    {
      LODWORD(v14[0]) = *(_DWORD *)a2;
      v17 = v14;
      v18 = 4;
      if ( a4 )
      {
        v10 = -1;
        do
          ++v10;
        while ( *(_WORD *)&a4[2 * v10] );
        v11 = 2 * v10 + 2;
      }
      else
      {
        a4 = (char *)&qword_180010000;
        v11 = 2;
      }
      v14[8] = a4;
      v15 = v11;
      v16 = 0;
      tlgWriteTransfer_EventWriteTransfer(&dword_180014230, byte_180010D43, 0, 0);
    }
    v14[0] = a2;
    v14[1] = a1;
    ForEachRegSubKey__lambda_b2932f37bd01d37ef5d2c59b4ad9c5b6_(a3);
  }
  std::list<Command>::sort(a2 + 1);
  return a2;
}

```

## disassembly

```asm
0x18000b660  mov     [rsp-8+arg_0], rbx
0x18000b665  push    rbp
0x18000b666  push    rsi
0x18000b667  push    rdi
0x18000b668  push    r14
0x18000b66a  push    r15
0x18000b66c  lea     rbp, [rsp-37h]
0x18000b671  sub     rsp, 0C0h
0x18000b678  mov     rax, cs:__security_cookie
0x18000b67f  xor     rax, rsp
0x18000b682  mov     [rbp+57h+var_30], rax
0x18000b686  mov     rdi, r9
0x18000b689  mov     rsi, r8
0x18000b68c  mov     rbx, rdx
0x18000b68f  mov     r14, rcx
0x18000b692  mov     [rbp+57h+var_80], rdx
0x18000b696  xor     r15d, r15d
0x18000b699  mov     [rbp+57h+var_A0], r15d
0x18000b69d  mov     rcx, rdx; this
0x18000b6a0  call    ??0CommandSet@@QEAA@XZ; CommandSet::CommandSet(void)
0x18000b6a5  mov     [rbp+57h+var_A0], 1
0x18000b6ac  lea     rcx, [rbx+18h]; void *
0x18000b6b0  mov     rdx, rdi; Src
0x18000b6b3  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18000b6b8  mov     [rbp+57h+var_9C], 4
0x18000b6bf  lea     rax, [rbp+57h+var_9C]
0x18000b6c3  mov     [rsp+0E0h+pcbData], rax; pcbData
0x18000b6c8  mov     [rsp+0E0h+pvData], rbx; pvData
0x18000b6cd  mov     [rsp+0E0h+pdwType], r15; pdwType
0x18000b6d2  lea     r9d, [r15+10h]; dwFlags
0x18000b6d6  lea     r8, Value; "altitude"
0x18000b6dd  xor     edx, edx; lpSubKey
0x18000b6df  mov     rcx, rsi; hkey
0x18000b6e2  call    cs:__imp_RegGetValueW
0x18000b6e8  test    eax, eax
0x18000b6ea  mov     eax, cs:dword_180014230
0x18000b6f0  jnz     loc_18000B783
0x18000b6f6  cmp     eax, 4
0x18000b6f9  jbe     short loc_18000B76D
0x18000b6fb  mov     eax, [rbx]
0x18000b6fd  mov     dword ptr [rbp+57h+var_90], eax
0x18000b700  lea     rax, [rbp+57h+var_90]
0x18000b704  mov     [rbp+57h+var_40], rax
0x18000b708  mov     [rbp+57h+var_38], 4
0x18000b710  test    rdi, rdi
0x18000b713  jz      short loc_18000B72C
0x18000b715  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000b719  inc     rcx
0x18000b71c  cmp     [rdi+rcx*2], r15w
0x18000b721  jnz     short loc_18000B719
0x18000b723  lea     ecx, ds:2[rcx*2]
0x18000b72a  jmp     short loc_18000B738
0x18000b72c  lea     rdi, qword_180010000
0x18000b733  mov     ecx, 2
0x18000b738  mov     [rbp+57h+var_50], rdi
0x18000b73c  mov     [rbp+57h+var_48], ecx
0x18000b73f  mov     [rbp+57h+var_44], r15d
0x18000b743  lea     rax, [rbp+57h+var_70]
0x18000b747  mov     [rsp+0E0h+pvData], rax
0x18000b74c  mov     dword ptr [rsp+0E0h+pdwType], 4
0x18000b754  xor     r9d, r9d
0x18000b757  xor     r8d, r8d
0x18000b75a  lea     rdx, byte_180010D43
0x18000b761  lea     rcx, dword_180014230
0x18000b768  call    _tlgWriteTransfer_EventWriteTransfer
0x18000b76d  mov     [rbp+57h+var_90], rbx
0x18000b771  mov     [rbp+57h+var_88], r14
0x18000b775  lea     rdx, [rbp+57h+var_90]
0x18000b779  mov     rcx, rsi; hKey
0x18000b77c  call    ForEachRegSubKey__lambda_b2932f37bd01d37ef5d2c59b4ad9c5b6___; ForEachRegSubKey__lambda_b2932f37bd01d37ef5d2c59b4ad9c5b6_
0x18000b781  jmp     short loc_18000B7A5
0x18000b783  mov     ecx, 2
0x18000b788  cmp     eax, ecx
0x18000b78a  jbe     short loc_18000B7A5
0x18000b78c  mov     [rbp+57h+var_90], rdi
0x18000b790  lea     rax, [rbp+57h+var_90]
0x18000b794  mov     [rsp+0E0h+pdwType], rax
0x18000b799  lea     rdx, byte_180010D8B
0x18000b7a0  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18000b7a5  lea     rcx, [rbx+8]
0x18000b7a9  call    ?sort@?$list@UCommand@@V?$allocator@UCommand@@@std@@@std@@QEAAXXZ; std::list<Command>::sort(void)
0x18000b7ae  mov     rax, rbx
0x18000b7b1  mov     rcx, [rbp+57h+var_30]
0x18000b7b5  xor     rcx, rsp; StackCookie
0x18000b7b8  call    __security_check_cookie
0x18000b7bd  mov     rbx, [rsp+0E0h+arg_0]
0x18000b7c5  add     rsp, 0C0h
0x18000b7cc  pop     r15
0x18000b7ce  pop     r14
0x18000b7d0  pop     rdi
0x18000b7d1  pop     rsi
0x18000b7d2  pop     rbp
0x18000b7d3  retn
```
