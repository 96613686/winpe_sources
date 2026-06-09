# CMsmqVssWriter::AddServiceMapping(IVssCreateWriterMetadata *,wchar_t const *)

- ea: `0x18008e270`
- end: `0x18008e521`
- name: `?AddServiceMapping@CMsmqVssWriter@@AEAAJPEAVIVssCreateWriterMetadata@@PEB_W@Z`
- size: `689`
- prototype: `__int64 __fastcall(CMsmqVssWriter *__hidden this, struct IVssCreateWriterMetadata *, const wchar_t *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x18008dd84`

## callees

- `0x18000bb04`
- `0x18002c61c`
- `0x18008e270`
- `0x18009a590`
- `0x18009bd1c`
- `0x1800e4010`

## import_xrefs

- `msvcrt!free` at `0x18008e3bc`
- `msvcrt!free` at `0x18008e424`
- `msvcrt!free` at `0x18008e48b`
- `msvcrt!free` at `0x18008e495`
- `msvcrt!free` at `0x18008e4df`
- `msvcrt!free` at `0x18008e4e9`
- `msvcrt!free` at `0x18008e4f5`
- `msvcrt!free` at `0x18008e4ff`
- `msvcrt!free` at `0x18008e3bc`
- `msvcrt!free` at `0x18008e424`
- `msvcrt!free` at `0x18008e48b`
- `msvcrt!free` at `0x18008e495`
- `msvcrt!free` at `0x18008e4df`
- `msvcrt!free` at `0x18008e4e9`
- `msvcrt!free` at `0x18008e4f5`
- `msvcrt!free` at `0x18008e4ff`

## string_xrefs

- `0x18008e328`: `QueuesAliasPath`
- `0x18008e2f6`: `writer/mqwriter`
- `0x18008e3aa`: `writer/mqwriter`
- `0x18008e412`: `writer/mqwriter`
- `0x18008e479`: `writer/mqwriter`
- `0x18008e4cd`: `writer/mqwriter`
- `0x18008e2d2`: `config`
- `0x18008e3f3`: `config`
- `0x18008e3e1`: `*.xml`
- `0x18008e4ab`: `*.xml`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CMsmqVssWriter::AddServiceMapping(
        CMsmqVssWriter *this,
        struct IVssCreateWriterMetadata *a2,
        const wchar_t *a3)
{
  int v6; // eax
  unsigned int v7; // ebx
  void *v9; // rdi
  int v10; // eax
  int v11; // eax
  wchar_t *v12; // rbx
  int v13; // eax
  unsigned int v14; // esi
  int v15; // eax
  int v16; // [rsp+28h] [rbp-90h]
  int v17; // [rsp+70h] [rbp-48h] BYREF
  __int64 v18; // [rsp+78h] [rbp-40h]
  const wchar_t *v19; // [rsp+80h] [rbp-38h]
  int v20; // [rsp+88h] [rbp-30h]
  __int64 v21; // [rsp+90h] [rbp-28h]
  void *Block; // [rsp+C8h] [rbp+10h] BYREF
  wchar_t *v23; // [rsp+D8h] [rbp+20h]

  v6 = (*(__int64 (__fastcall **)(struct IVssCreateWriterMetadata *, __int64, const wchar_t *, const wchar_t *, _QWORD, _QWORD, _DWORD, _BYTE, _BYTE, char, char, _DWORD))(*(_QWORD *)a2 + 16LL))(
         a2,
         2,
         L"config",
         L"mapping",
         0,
         0,
         0,
         0,
         0,
         1,
         1,
         0);
  v7 = v6;
  if ( v6 < 0 )
  {
    LogMsgHR(v6, (wchar_t *)L"writer/mqwriter", 0x424u);
    return v7;
  }
  Block = 0;
  v17 = 0;
  v18 = *((_QWORD *)this + 4);
  v19 = L"QueuesAliasPath";
  v20 = 0;
  v21 = -2147483646;
  CmQueryValue((const struct RegEntry *)&v17, (wchar_t **)&Block);
  v9 = Block;
  if ( !Block )
  {
    v9 = MmAllocate(0x20Au);
    Block = v9;
    v10 = StringCchPrintfW((wchar_t *)v9, 0x105u, L"%s\\%s", a3, L"mapping");
    v7 = v10;
    if ( v10 < 0 )
    {
      LogMsgHR(v10, (wchar_t *)L"writer/mqwriter", 0x438u);
      free(v9);
      return v7;
    }
  }
  LOBYTE(v16) = 0;
  v11 = (*(__int64 (__fastcall **)(struct IVssCreateWriterMetadata *, const wchar_t *, const wchar_t *, void *, const wchar_t *, int, _QWORD, int))(*(_QWORD *)a2 + 40LL))(
          a2,
          L"config",
          L"mapping",
          v9,
          L"*.xml",
          v16,
          0,
          3855);
  v7 = v11;
  if ( v11 < 0 )
  {
    LogMsgHR(v11, (wchar_t *)L"writer/mqwriter", 0x44Cu);
    free(v9);
    return v7;
  }
  v12 = (wchar_t *)MmAllocate(0x20Au);
  v23 = v12;
  v13 = StringCchPrintfW(v12, 0x105u, L"%s\\%s\\%s", a3, L"Restore", L"mapping");
  v14 = v13;
  if ( v13 < 0 )
  {
    LogMsgHR(v13, (wchar_t *)L"writer/mqwriter", 0x460u);
    free(v12);
    free(v9);
    return v14;
  }
  v15 = (*(__int64 (__fastcall **)(struct IVssCreateWriterMetadata *, void *, const wchar_t *, _QWORD, wchar_t *))(*(_QWORD *)a2 + 56LL))(
          a2,
          v9,
          L"*.xml",
          0,
          v12);
  v14 = v15;
  if ( v15 < 0 )
  {
    LogMsgHR(v15, (wchar_t *)L"writer/mqwriter", 0x474u);
    free(v12);
    free(v9);
    return v14;
  }
  free(v12);
  free(v9);
  return 0;
}

```

## disassembly

```asm
0x18008e270  mov     [rsp+arg_0], rbx
0x18008e275  mov     [rsp+arg_10], rsi
0x18008e27a  push    rdi
0x18008e27b  push    r14
0x18008e27d  push    r15
0x18008e27f  sub     rsp, 0A0h
0x18008e286  mov     rsi, r8
0x18008e289  mov     r14, rdx
0x18008e28c  mov     rdi, rcx
0x18008e28f  mov     rax, [rdx]
0x18008e292  mov     [rsp+0B8h+var_60], 0
0x18008e29a  mov     [rsp+0B8h+var_68], 1
0x18008e29f  mov     [rsp+0B8h+var_70], 1
0x18008e2a4  mov     [rsp+0B8h+var_78], 0
0x18008e2a9  mov     byte ptr [rsp+0B8h+var_80], 0
0x18008e2ae  mov     dword ptr [rsp+0B8h+var_88], 0
0x18008e2b6  mov     [rsp+0B8h+var_90], 0
0x18008e2bf  mov     [rsp+0B8h+var_98], 0
0x18008e2c8  lea     r15, aMapping; "mapping"
0x18008e2cf  mov     r9, r15
0x18008e2d2  lea     r8, aConfig; "config"
0x18008e2d9  mov     edx, 2
0x18008e2de  mov     rcx, r14
0x18008e2e1  mov     rax, [rax+10h]
0x18008e2e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e2ea  mov     ebx, eax
0x18008e2ec  test    eax, eax
0x18008e2ee  jns     short loc_18008E30B
0x18008e2f0  mov     r8d, 424h; unsigned __int16
0x18008e2f6  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x18008e2fd  mov     ecx, eax; int
0x18008e2ff  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18008e304  mov     eax, ebx
0x18008e306  jmp     loc_18008E508
0x18008e30b  mov     [rsp+0B8h+Block], 0
0x18008e317  mov     [rsp+0B8h+var_48], 0
0x18008e31f  mov     rax, [rdi+20h]
0x18008e323  mov     [rsp+0B8h+var_40], rax
0x18008e328  lea     rax, aQueuesaliaspat; "QueuesAliasPath"
0x18008e32f  mov     [rsp+0B8h+var_38], rax
0x18008e337  mov     [rsp+0B8h+var_30], 0
0x18008e342  mov     [rsp+0B8h+var_28], 0FFFFFFFF80000002h
0x18008e34e  lea     rdx, [rsp+0B8h+Block]; wchar_t **
0x18008e356  lea     rcx, [rsp+0B8h+var_48]; struct RegEntry *
0x18008e35b  call    ?CmQueryValue@@YAXAEBVRegEntry@@PEAPEA_W@Z; CmQueryValue(RegEntry const &,wchar_t * *)
0x18008e360  mov     rdi, [rsp+0B8h+Block]
0x18008e368  test    rdi, rdi
0x18008e36b  jnz     short loc_18008E3C8
0x18008e36d  mov     ecx, 20Ah; unsigned __int64
0x18008e372  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x18008e377  mov     rdi, rax
0x18008e37a  mov     [rsp+0B8h+Block], rax
0x18008e382  mov     [rsp+0B8h+var_98], r15
0x18008e387  mov     r9, rsi
0x18008e38a  lea     r8, aSS_3; "%s\\%s"
0x18008e391  mov     edx, 105h; unsigned __int64
0x18008e396  mov     rcx, rax; wchar_t *
0x18008e399  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18008e39e  mov     ebx, eax
0x18008e3a0  test    eax, eax
0x18008e3a2  jns     short loc_18008E3C8
0x18008e3a4  mov     r8d, 438h; unsigned __int16
0x18008e3aa  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x18008e3b1  mov     ecx, eax; int
0x18008e3b3  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18008e3b8  nop
0x18008e3b9  mov     rcx, rdi; Block
0x18008e3bc  call    cs:__imp_free
0x18008e3c2  nop
0x18008e3c3  jmp     loc_18008E304
0x18008e3c8  mov     rax, [r14]
0x18008e3cb  mov     [rsp+0B8h+var_80], 0F0Fh
0x18008e3d3  mov     [rsp+0B8h+var_88], 0
0x18008e3dc  mov     byte ptr [rsp+0B8h+var_90], 0
0x18008e3e1  lea     rcx, aXml_0; "*.xml"
0x18008e3e8  mov     [rsp+0B8h+var_98], rcx
0x18008e3ed  mov     r9, rdi
0x18008e3f0  mov     r8, r15
0x18008e3f3  lea     rdx, aConfig; "config"
0x18008e3fa  mov     rcx, r14
0x18008e3fd  mov     rax, [rax+28h]
0x18008e401  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e406  mov     ebx, eax
0x18008e408  test    eax, eax
0x18008e40a  jns     short loc_18008E430
0x18008e40c  mov     r8d, 44Ch; unsigned __int16
0x18008e412  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x18008e419  mov     ecx, eax; int
0x18008e41b  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18008e420  nop
0x18008e421  mov     rcx, rdi; Block
0x18008e424  call    cs:__imp_free
0x18008e42a  nop
0x18008e42b  jmp     loc_18008E304
0x18008e430  mov     ecx, 20Ah; unsigned __int64
0x18008e435  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x18008e43a  mov     rbx, rax
0x18008e43d  mov     [rsp+0B8h+arg_18], rax
0x18008e445  mov     [rsp+0B8h+var_90], r15
0x18008e44a  lea     rax, aRestore; "Restore"
0x18008e451  mov     [rsp+0B8h+var_98], rax
0x18008e456  mov     r9, rsi
0x18008e459  lea     r8, aSSS; "%s\\%s\\%s"
0x18008e460  mov     edx, 105h; unsigned __int64
0x18008e465  mov     rcx, rbx; wchar_t *
0x18008e468  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18008e46d  mov     esi, eax
0x18008e46f  test    eax, eax
0x18008e471  jns     short loc_18008E4A0
0x18008e473  mov     r8d, 460h; unsigned __int16
0x18008e479  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x18008e480  mov     ecx, eax; int
0x18008e482  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18008e487  nop
0x18008e488  mov     rcx, rbx; Block
0x18008e48b  call    cs:__imp_free
0x18008e491  nop
0x18008e492  mov     rcx, rdi; Block
0x18008e495  call    cs:__imp_free
0x18008e49b  nop
0x18008e49c  mov     eax, esi
0x18008e49e  jmp     short loc_18008E508
0x18008e4a0  mov     rax, [r14]
0x18008e4a3  mov     [rsp+0B8h+var_98], rbx
0x18008e4a8  xor     r9d, r9d
0x18008e4ab  lea     r8, aXml_0; "*.xml"
0x18008e4b2  mov     rdx, rdi
0x18008e4b5  mov     rcx, r14
0x18008e4b8  mov     rax, [rax+38h]
0x18008e4bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e4c1  mov     esi, eax
0x18008e4c3  test    eax, eax
0x18008e4c5  jns     short loc_18008E4F2
0x18008e4c7  mov     r8d, 474h; unsigned __int16
0x18008e4cd  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x18008e4d4  mov     ecx, eax; int
0x18008e4d6  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18008e4db  nop
0x18008e4dc  mov     rcx, rbx; Block
0x18008e4df  call    cs:__imp_free
0x18008e4e5  nop
0x18008e4e6  mov     rcx, rdi; Block
0x18008e4e9  call    cs:__imp_free
0x18008e4ef  nop
0x18008e4f0  jmp     short loc_18008E49C
0x18008e4f2  mov     rcx, rbx; Block
0x18008e4f5  call    cs:__imp_free
0x18008e4fb  nop
0x18008e4fc  mov     rcx, rdi; Block
0x18008e4ff  call    cs:__imp_free
0x18008e505  nop
0x18008e506  xor     eax, eax
0x18008e508  lea     r11, [rsp+0B8h+var_18]
0x18008e510  mov     rbx, [r11+20h]
0x18008e514  mov     rsi, [r11+30h]
0x18008e518  mov     rsp, r11
0x18008e51b  pop     r15
0x18008e51d  pop     r14
0x18008e51f  pop     rdi
0x18008e520  retn
```
