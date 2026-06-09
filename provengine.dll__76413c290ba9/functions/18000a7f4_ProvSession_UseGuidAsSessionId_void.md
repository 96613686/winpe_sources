# ProvSession::UseGuidAsSessionId(void)

- ea: `0x18000a7f4`
- end: `0x18000a96f`
- name: `?UseGuidAsSessionId@ProvSession@@AEAAJXZ`
- size: `379`
- prototype: `__int64 __fastcall(ProvSession *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180007cc0`

## callees

- `0x1800010c8`
- `0x1800098dc`
- `0x18000a7f4`
- `0x18000b030`
- `0x180043750`

## import_xrefs

- `RPCRT4!RpcStringFreeW` at `0x18000a94d`
- `RPCRT4!RpcStringFreeW` at `0x18000a94d`
- `RPCRT4!UuidCreate` at `0x18000a870`
- `RPCRT4!UuidCreate` at `0x18000a870`
- `RPCRT4!UuidToStringW` at `0x18000a89c`
- `RPCRT4!UuidToStringW` at `0x18000a89c`

## string_xrefs

- `0x18000a8bd`: `onecoreuap\admin\prov\multivariant\common\src\commonutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ProvSession::UseGuidAsSessionId(ProvSession *this)
{
  _WORD *v2; // rcx
  RPC_STATUS v3; // eax
  signed int v4; // ebx
  __int64 v5; // rdx
  RPC_STATUS v6; // eax
  unsigned __int64 v7; // r8
  int v9; // [rsp+20h] [rbp-29h]
  RPC_WSTR StringUuid; // [rsp+30h] [rbp-19h] BYREF
  UUID Uuid; // [rsp+38h] [rbp-11h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v12[2]; // [rsp+48h] [rbp-1h] BYREF
  RPC_WSTR *p_StringUuid; // [rsp+68h] [rbp+1Fh]
  __int64 v14; // [rsp+70h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  if ( (unsigned int)dword_18005A000 > 4 )
    tlgWriteTransfer_EventWriteTransfer((__int64)&dword_18005A000, (unsigned __int8 *)&dword_18004E4A4, 0, 0, 2u, v12);
  Uuid = 0;
  if ( *((_QWORD *)this + 6) < 8u )
    v2 = (_WORD *)((char *)this + 24);
  else
    v2 = (_WORD *)*((_QWORD *)this + 3);
  *((_QWORD *)this + 5) = 0;
  *v2 = 0;
  v3 = UuidCreate(&Uuid);
  v4 = v3;
  if ( v3 > 0 )
    v4 = (unsigned __int16)v3 | 0x80070000;
  if ( v4 < 0 )
  {
    v5 = 102;
    goto LABEL_14;
  }
  StringUuid = 0;
  v6 = UuidToStringW(&Uuid, &StringUuid);
  v4 = v6;
  if ( v6 > 0 )
    v4 = (unsigned __int16)v6 | 0x80070000;
  if ( v4 < 0 )
  {
    v5 = 105;
LABEL_14:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\common\\src\\commonutils.cpp",
      (const char *)(unsigned int)v4,
      v9);
    if ( (unsigned int)dword_18005A000 > 2 )
    {
      LODWORD(StringUuid) = v4;
      p_StringUuid = &StringUuid;
      v14 = 4;
      tlgWriteTransfer_EventWriteTransfer((__int64)&dword_18005A000, (unsigned __int8 *)word_18004E332, 0, 0, 3u, v12);
    }
    return (unsigned int)v4;
  }
  v12[0].Ptr = (ULONGLONG)&StringUuid;
  LOBYTE(v12[0].Size) = 1;
  if ( *StringUuid )
  {
    v7 = -1;
    do
      ++v7;
    while ( StringUuid[v7] );
  }
  else
  {
    v7 = 0;
  }
  std::wstring::assign((_QWORD *)this + 3, (char *)StringUuid, v7);
  RpcStringFreeW(&StringUuid);
  return 0;
}

```

## disassembly

```asm
0x18000a7f4  push    rbp
0x18000a7f6  push    rbx
0x18000a7f7  push    rsi
0x18000a7f8  push    rdi
0x18000a7f9  lea     rbp, [rsp-3Fh]
0x18000a7fe  sub     rsp, 88h
0x18000a805  mov     rax, cs:__security_cookie
0x18000a80c  xor     rax, rsp
0x18000a80f  mov     [rbp+57h+var_28], rax
0x18000a813  mov     rdi, rcx
0x18000a816  mov     eax, cs:dword_18005A000
0x18000a81c  cmp     eax, 4
0x18000a81f  jbe     short loc_18000A84B
0x18000a821  lea     rax, [rbp+57h+var_58]
0x18000a825  mov     [rsp+0A0h+var_78], rax
0x18000a82a  mov     [rsp+0A0h+var_80], 2; int
0x18000a832  xor     r9d, r9d
0x18000a835  xor     r8d, r8d
0x18000a838  lea     rdx, dword_18004E4A4
0x18000a83f  lea     rcx, dword_18005A000
0x18000a846  call    _tlgWriteTransfer_EventWriteTransfer
0x18000a84b  xorps   xmm0, xmm0
0x18000a84e  movups  xmmword ptr [rbp+57h+Uuid.Data1], xmm0
0x18000a852  cmp     qword ptr [rdi+30h], 8
0x18000a857  jb      short loc_18000A85F
0x18000a859  mov     rcx, [rdi+18h]
0x18000a85d  jmp     short loc_18000A863
0x18000a85f  lea     rcx, [rdi+18h]
0x18000a863  xor     esi, esi
0x18000a865  mov     [rdi+28h], rsi
0x18000a869  mov     [rcx], si
0x18000a86c  lea     rcx, [rbp+57h+Uuid]; Uuid
0x18000a870  call    cs:__imp_UuidCreate
0x18000a876  mov     ebx, eax
0x18000a878  test    eax, eax
0x18000a87a  jle     short loc_18000A885
0x18000a87c  movzx   ebx, ax
0x18000a87f  or      ebx, 80070000h
0x18000a885  test    ebx, ebx
0x18000a887  jns     short loc_18000A890
0x18000a889  mov     edx, 66h ; 'f'
0x18000a88e  jmp     short loc_18000A8BA
0x18000a890  mov     [rbp+57h+StringUuid], rsi
0x18000a894  lea     rdx, [rbp+57h+StringUuid]; StringUuid
0x18000a898  lea     rcx, [rbp+57h+Uuid]; Uuid
0x18000a89c  call    cs:__imp_UuidToStringW
0x18000a8a2  mov     ebx, eax
0x18000a8a4  test    eax, eax
0x18000a8a6  jle     short loc_18000A8B1
0x18000a8a8  movzx   ebx, ax
0x18000a8ab  or      ebx, 80070000h
0x18000a8b1  test    ebx, ebx
0x18000a8b3  jns     short loc_18000A917
0x18000a8b5  mov     edx, 69h ; 'i'; void *
0x18000a8ba  mov     r9d, ebx; char *
0x18000a8bd  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18000a8c4  mov     rcx, [rbp+5Fh]; this
0x18000a8c8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a8cd  mov     eax, cs:dword_18005A000
0x18000a8d3  cmp     eax, 2
0x18000a8d6  jbe     short loc_18000A955
0x18000a8d8  mov     dword ptr [rbp+57h+StringUuid], ebx
0x18000a8db  lea     rax, [rbp+57h+StringUuid]
0x18000a8df  mov     [rbp+57h+var_38], rax
0x18000a8e3  mov     [rbp+57h+var_30], 4
0x18000a8eb  lea     rax, [rbp+57h+var_58]
0x18000a8ef  mov     [rsp+0A0h+var_78], rax
0x18000a8f4  mov     [rsp+0A0h+var_80], 3
0x18000a8fc  xor     r9d, r9d
0x18000a8ff  xor     r8d, r8d
0x18000a902  lea     rdx, word_18004E332
0x18000a909  lea     rcx, dword_18005A000
0x18000a910  call    _tlgWriteTransfer_EventWriteTransfer
0x18000a915  jmp     short loc_18000A955
0x18000a917  lea     rax, [rbp+57h+StringUuid]
0x18000a91b  mov     [rbp+57h+var_58], rax
0x18000a91f  mov     [rbp+57h+var_50], 1
0x18000a923  mov     rdx, [rbp+57h+StringUuid]; Src
0x18000a927  cmp     [rdx], si
0x18000a92a  jnz     short loc_18000A931
0x18000a92c  mov     r8, rsi
0x18000a92f  jmp     short loc_18000A93F
0x18000a931  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000a935  inc     r8
0x18000a938  cmp     [rdx+r8*2], si
0x18000a93d  jnz     short loc_18000A935
0x18000a93f  lea     rcx, [rdi+18h]; void *
0x18000a943  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18000a948  nop
0x18000a949  lea     rcx, [rbp+57h+StringUuid]; String
0x18000a94d  call    cs:__imp_RpcStringFreeW
0x18000a953  mov     ebx, esi
0x18000a955  mov     eax, ebx
0x18000a957  mov     rcx, [rbp+57h+var_28]
0x18000a95b  xor     rcx, rsp; StackCookie
0x18000a95e  call    __security_check_cookie
0x18000a963  add     rsp, 88h
0x18000a96a  pop     rdi
0x18000a96b  pop     rsi
0x18000a96c  pop     rbx
0x18000a96d  pop     rbp
0x18000a96e  retn
```
