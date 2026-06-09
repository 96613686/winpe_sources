# RegistryConfig::ParseCommandSet(HKEY__ *,ushort const *)

- ea: `0x18000bce8`
- end: `0x18000be63`
- name: `?ParseCommandSet@RegistryConfig@@AEAA?AUCommandSet@@PEAUHKEY__@@PEBG@Z`
- size: `379`
- prototype: `struct CommandSet __high(HKEY, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000be6c`

## callees

- `0x180001090`
- `0x18000134c`
- `0x180007fac`
- `0x18000a418`
- `0x18000a5f4`
- `0x18000bce8`
- `0x18000c47c`
- `0x18000ccc0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000bd6a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000bd6a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 **__fastcall RegistryConfig::ParseCommandSet(__int64 a1, __int64 **a2, HKEY a3, __int64 *a4)
{
  int v8; // r8d
  int v9; // r9d
  __int64 v10; // rcx
  int v11; // ecx
  DWORD pcbData[3]; // [rsp+44h] [rbp-45h] BYREF
  __int64 v14[4]; // [rsp+50h] [rbp-39h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v15; // [rsp+70h] [rbp-19h] BYREF
  __int64 *v16; // [rsp+90h] [rbp+7h]
  int v17; // [rsp+98h] [rbp+Fh]
  int v18; // [rsp+9Ch] [rbp+13h]
  __int64 *v19; // [rsp+A0h] [rbp+17h]
  __int64 v20; // [rsp+A8h] [rbp+1Fh]

  v14[2] = (__int64)a2;
  CommandSet::CommandSet((CommandSet *)a2);
  std::wstring::assign(a2 + 3, a4);
  pcbData[0] = 4;
  if ( RegGetValueW(a3, 0, L"altitude", 0x10u, 0, a2, pcbData) )
  {
    if ( (unsigned int)dword_180014230 > 2 )
    {
      v14[0] = (__int64)a4;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        2,
        (unsigned int)byte_180010D8B,
        v8,
        v9,
        (__int64)v14);
    }
  }
  else
  {
    if ( (unsigned int)dword_180014230 > 4 )
    {
      LODWORD(v14[0]) = *(_DWORD *)a2;
      v19 = v14;
      v20 = 4;
      if ( a4 )
      {
        v10 = -1;
        do
          ++v10;
        while ( *((_WORD *)a4 + v10) );
        v11 = 2 * v10 + 2;
      }
      else
      {
        a4 = &qword_180010000;
        v11 = 2;
      }
      v16 = a4;
      v17 = v11;
      v18 = 0;
      tlgWriteTransfer_EventWriteTransfer((__int64)&dword_180014230, (unsigned __int8 *)byte_180010D43, 0, 0, 4u, &v15);
    }
    v14[0] = (__int64)a2;
    v14[1] = a1;
    ForEachRegSubKey__lambda_b2932f37bd01d37ef5d2c59b4ad9c5b6_(a3, v14);
  }
  std::list<Command>::sort(a2 + 1);
  return a2;
}

```

## disassembly

```asm
0x18000bce8  mov     [rsp-8+arg_0], rbx
0x18000bced  push    rbp
0x18000bcee  push    rsi
0x18000bcef  push    rdi
0x18000bcf0  push    r14
0x18000bcf2  push    r15
0x18000bcf4  lea     rbp, [rsp-37h]
0x18000bcf9  sub     rsp, 0C0h
0x18000bd00  mov     rax, cs:__security_cookie
0x18000bd07  xor     rax, rsp
0x18000bd0a  mov     [rbp+57h+var_30], rax
0x18000bd0e  mov     rdi, r9
0x18000bd11  mov     rsi, r8
0x18000bd14  mov     rbx, rdx
0x18000bd17  mov     r14, rcx
0x18000bd1a  mov     [rbp+57h+var_80], rdx
0x18000bd1e  xor     r15d, r15d
0x18000bd21  mov     [rbp+57h+var_A0], r15d
0x18000bd25  mov     rcx, rdx; this
0x18000bd28  call    ??0CommandSet@@QEAA@XZ; CommandSet::CommandSet(void)
0x18000bd2d  mov     [rbp+57h+var_A0], 1
0x18000bd34  lea     rcx, [rbx+18h]; void *
0x18000bd38  mov     rdx, rdi; Src
0x18000bd3b  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18000bd40  mov     [rbp+57h+var_9C], 4
0x18000bd47  lea     rax, [rbp+57h+var_9C]
0x18000bd4b  mov     [rsp+0E0h+pcbData], rax; pcbData
0x18000bd50  mov     [rsp+0E0h+pvData], rbx; pvData
0x18000bd55  mov     [rsp+0E0h+pdwType], r15; pdwType
0x18000bd5a  lea     r9d, [r15+10h]; dwFlags
0x18000bd5e  lea     r8, Value; "altitude"
0x18000bd65  xor     edx, edx; lpSubKey
0x18000bd67  mov     rcx, rsi; hkey
0x18000bd6a  call    cs:__imp_RegGetValueW
0x18000bd71  nop     dword ptr [rax+rax+00h]
0x18000bd76  test    eax, eax
0x18000bd78  mov     eax, cs:dword_180014230
0x18000bd7e  jnz     loc_18000BE11
0x18000bd84  cmp     eax, 4
0x18000bd87  jbe     short loc_18000BDFB
0x18000bd89  mov     eax, [rbx]
0x18000bd8b  mov     dword ptr [rbp+57h+var_90], eax
0x18000bd8e  lea     rax, [rbp+57h+var_90]
0x18000bd92  mov     [rbp+57h+var_40], rax
0x18000bd96  mov     [rbp+57h+var_38], 4
0x18000bd9e  test    rdi, rdi
0x18000bda1  jz      short loc_18000BDBA
0x18000bda3  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000bda7  inc     rcx
0x18000bdaa  cmp     [rdi+rcx*2], r15w
0x18000bdaf  jnz     short loc_18000BDA7
0x18000bdb1  lea     ecx, ds:2[rcx*2]
0x18000bdb8  jmp     short loc_18000BDC6
0x18000bdba  lea     rdi, qword_180010000
0x18000bdc1  mov     ecx, 2
0x18000bdc6  mov     [rbp+57h+var_50], rdi
0x18000bdca  mov     [rbp+57h+var_48], ecx
0x18000bdcd  mov     [rbp+57h+var_44], r15d
0x18000bdd1  lea     rax, [rbp+57h+var_70]
0x18000bdd5  mov     [rsp+0E0h+pvData], rax
0x18000bdda  mov     dword ptr [rsp+0E0h+pdwType], 4
0x18000bde2  xor     r9d, r9d
0x18000bde5  xor     r8d, r8d
0x18000bde8  lea     rdx, byte_180010D43
0x18000bdef  lea     rcx, dword_180014230
0x18000bdf6  call    _tlgWriteTransfer_EventWriteTransfer
0x18000bdfb  mov     [rbp+57h+var_90], rbx
0x18000bdff  mov     [rbp+57h+var_88], r14
0x18000be03  lea     rdx, [rbp+57h+var_90]
0x18000be07  mov     rcx, rsi; hKey
0x18000be0a  call    ForEachRegSubKey__lambda_b2932f37bd01d37ef5d2c59b4ad9c5b6___; ForEachRegSubKey__lambda_b2932f37bd01d37ef5d2c59b4ad9c5b6_
0x18000be0f  jmp     short loc_18000BE33
0x18000be11  mov     ecx, 2
0x18000be16  cmp     eax, ecx
0x18000be18  jbe     short loc_18000BE33
0x18000be1a  mov     [rbp+57h+var_90], rdi
0x18000be1e  lea     rax, [rbp+57h+var_90]
0x18000be22  mov     [rsp+0E0h+pdwType], rax
0x18000be27  lea     rdx, byte_180010D8B
0x18000be2e  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18000be33  lea     rcx, [rbx+8]
0x18000be37  call    ?sort@?$list@UCommand@@V?$allocator@UCommand@@@std@@@std@@QEAAXXZ; std::list<Command>::sort(void)
0x18000be3c  mov     rax, rbx
0x18000be3f  mov     rcx, [rbp+57h+var_30]
0x18000be43  xor     rcx, rsp; StackCookie
0x18000be46  call    __security_check_cookie
0x18000be4b  mov     rbx, [rsp+0E0h+arg_0]
0x18000be53  add     rsp, 0C0h
0x18000be5a  pop     r15
0x18000be5c  pop     r14
0x18000be5e  pop     rdi
0x18000be5f  pop     rsi
0x18000be60  pop     rbp
0x18000be61  retn
```
