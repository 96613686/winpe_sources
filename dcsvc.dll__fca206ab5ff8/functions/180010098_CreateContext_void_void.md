# CreateContext(void *,void * *)

- ea: `0x180010098`
- end: `0x1800101b0`
- name: `?CreateContext@@YAJPEAXPEAPEAX@Z`
- size: `280`
- prototype: `__int64 __fastcall(void *, UUID **)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180011930`

## callees

- `0x180001284`
- `0x180001cf0`
- `0x1800026c8`
- `0x180010098`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180010148`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180010148`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800100d7`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800100d7`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x180010113`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x180010113`
- `RPCRT4!UuidCreateSequential` at `0x18001013a`
- `RPCRT4!UuidCreateSequential` at `0x18001013a`

## string_xrefs

- `0x180010159`: `CreateContext`

## pseudocode

```c
__int64 __fastcall CreateContext(void *a1, UUID **a2)
{
  unsigned int v3; // edi
  UUID *v4; // rbx
  __int64 v5; // rcx
  __int64 v6; // r8
  __int64 v7; // r9
  unsigned int v9; // [rsp+30h] [rbp-98h] BYREF
  const char *v10; // [rsp+38h] [rbp-90h] BYREF
  _DWORD RpcCallAttributes[2]; // [rsp+40h] [rbp-88h] BYREF
  _BYTE v12[56]; // [rsp+48h] [rbp-80h] BYREF
  unsigned int v13; // [rsp+80h] [rbp-48h]

  if ( a2 )
  {
    *a2 = 0;
    v4 = (UUID *)malloc(0x14u);
    if ( !v4 )
    {
      v3 = -2147024882;
      goto LABEL_9;
    }
    RpcCallAttributes[0] = 2;
    RpcCallAttributes[1] = 16;
    memset_0(v12, 0, 0x68u);
    if ( RpcServerInqCallAttributesW(0, RpcCallAttributes) )
    {
      v4[1].Data1 = 0;
      v3 = -2147418113;
      goto LABEL_9;
    }
    v3 = 0;
    v4[1].Data1 = v13;
    UuidCreateSequential(v4);
    *a2 = v4;
  }
  else
  {
    v3 = -2147024809;
  }
  v4 = 0;
LABEL_9:
  free(v4);
  if ( (unsigned int)dword_18001B0E8 > 5 )
  {
    v9 = v3;
    v10 = "CreateContext";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v5,
      (__int64)byte_180017603,
      v6,
      v7,
      (const unsigned __int16 **)&v10,
      (__int64)&v9);
  }
  return v3;
}

```

## disassembly

```asm
0x180010098  mov     [rsp+arg_0], rbx
0x18001009d  mov     [rsp+arg_10], rsi
0x1800100a2  push    rdi
0x1800100a3  sub     rsp, 0C0h
0x1800100aa  mov     rax, cs:__security_cookie
0x1800100b1  xor     rax, rsp
0x1800100b4  mov     [rsp+0C8h+var_18], rax
0x1800100bc  mov     rsi, rdx
0x1800100bf  test    rdx, rdx
0x1800100c2  jnz     short loc_1800100CB
0x1800100c4  mov     edi, 80070057h
0x1800100c9  jmp     short loc_180010143
0x1800100cb  mov     ecx, 14h; Size
0x1800100d0  mov     qword ptr [rdx], 0
0x1800100d7  call    cs:__imp_malloc
0x1800100dd  mov     rbx, rax
0x1800100e0  test    rax, rax
0x1800100e3  jnz     short loc_1800100EC
0x1800100e5  mov     edi, 8007000Eh
0x1800100ea  jmp     short loc_180010145
0x1800100ec  xor     edx, edx; Val
0x1800100ee  mov     [rsp+0C8h+RpcCallAttributes], 2
0x1800100f6  lea     rcx, [rsp+0C8h+var_80]; void *
0x1800100fb  mov     [rsp+0C8h+var_84], 10h
0x180010103  lea     r8d, [rdx+68h]; Size
0x180010107  call    memset_0
0x18001010c  lea     rdx, [rsp+0C8h+RpcCallAttributes]; RpcCallAttributes
0x180010111  xor     ecx, ecx; ClientBinding
0x180010113  call    cs:__imp_RpcServerInqCallAttributesW
0x180010119  test    eax, eax
0x18001011b  jz      short loc_18001012B
0x18001011d  mov     dword ptr [rbx+10h], 0
0x180010124  mov     edi, 8000FFFFh
0x180010129  jmp     short loc_180010145
0x18001012b  mov     eax, [rsp+0C8h+var_48]
0x180010132  xor     edi, edi
0x180010134  mov     rcx, rbx; Uuid
0x180010137  mov     [rbx+10h], eax
0x18001013a  call    cs:__imp_UuidCreateSequential
0x180010140  mov     [rsi], rbx
0x180010143  xor     ebx, ebx
0x180010145  mov     rcx, rbx; Block
0x180010148  call    cs:__imp_free
0x18001014e  mov     eax, cs:dword_18001B0E8
0x180010154  cmp     eax, 5
0x180010157  jbe     short loc_180010189
0x180010159  lea     rax, aCreatecontext; "CreateContext"
0x180010160  mov     [rsp+0C8h+var_98], edi
0x180010164  mov     [rsp+0C8h+var_90], rax
0x180010169  lea     rdx, byte_180017603
0x180010170  lea     rax, [rsp+0C8h+var_98]
0x180010175  mov     [rsp+0C8h+var_A0], rax
0x18001017a  lea     rax, [rsp+0C8h+var_90]
0x18001017f  mov     [rsp+0C8h+var_A8], rax
0x180010184  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180010189  mov     eax, edi
0x18001018b  mov     rcx, [rsp+0C8h+var_18]
0x180010193  xor     rcx, rsp; StackCookie
0x180010196  call    __security_check_cookie
0x18001019b  lea     r11, [rsp+0C8h+var_8]
0x1800101a3  mov     rbx, [r11+10h]
0x1800101a7  mov     rsi, [r11+20h]
0x1800101ab  mov     rsp, r11
0x1800101ae  pop     rdi
0x1800101af  retn
```
