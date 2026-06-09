# PROTOCOL_BINDING_LIST::AddBinding(ushort const *,ushort const *)

- ea: `0x180051254`
- end: `0x180051400`
- name: `?AddBinding@PROTOCOL_BINDING_LIST@@QEAAJPEBG0@Z`
- size: `428`
- prototype: `__int64 __fastcall(PROTOCOL_BINDING_LIST *this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `6`
- callee_count: `7`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180015958`
- `0x18003d05c`
- `0x18004c94c`
- `0x18004e094`
- `0x18004eecc`
- `0x180051408`

## callees

- `0x180001234`
- `0x180001274`
- `0x18005106c`
- `0x180051170`
- `0x180051254`
- `0x180051630`
- `0x18006101a`

## import_xrefs

- `iisutil!PuDbgPrintError` at `0x180051334`
- `iisutil!PuDbgPrintError` at `0x1800513ea`
- `iisutil!PuDbgPrintError` at `0x180051334`
- `iisutil!PuDbgPrintError` at `0x1800513ea`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180051291`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180051291`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800512f4`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800512f4`

## string_xrefs

- `0x18005132d`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\protocol_binding.cxx`
- `0x1800513e3`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\protocol_binding.cxx`
- `0x1800513bb`: `Failed to allocated memory for protocol binding\n`
- `0x18005131c`: `PROTOCOL_BINDING_LIST::AddBinding`
- `0x1800513dc`: `PROTOCOL_BINDING_LIST::AddBinding`
- `0x180051310`: `Failed to initialize the protocol binding\n`
- `0x180051395`: `Failed to add the binding to the protocol binding\n`

## pseudocode

```c
__int64 __fastcall PROTOCOL_BINDING_LIST::AddBinding(
        PROTOCOL_BINDING_LIST *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  struct PROTOCOL_BINDING *ProtocolBinding; // rbx
  int v7; // r8d
  char *v8; // rax
  int v9; // edi
  _QWORD *v10; // rcx
  __int64 v11; // rdx

  ProtocolBinding = PROTOCOL_BINDING_LIST::FindProtocolBinding(this, a2);
  if ( ProtocolBinding )
  {
LABEL_10:
    v9 = PROTOCOL_BINDING::AddBinding(ProtocolBinding, a3, v7);
    if ( v9 >= 0 )
    {
      ++*((_DWORD *)this + 7);
    }
    else if ( (g_dwDebugFlags & 0xF) != 0 )
    {
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\protocol_binding.cxx",
        567,
        "PROTOCOL_BINDING_LIST::AddBinding",
        v9,
        "Failed to add the binding to the protocol binding\r\n");
    }
    return (unsigned int)v9;
  }
  v8 = (char *)operator new(0x498u);
  ProtocolBinding = (struct PROTOCOL_BINDING *)v8;
  if ( v8 )
  {
    STRU::STRU((STRU *)(v8 + 8));
    *((_DWORD *)ProtocolBinding + 280) = 0;
    memset_0((char *)ProtocolBinding + 72, 0, 0x418u);
    *((_DWORD *)ProtocolBinding + 286) = 0;
    *((_QWORD *)ProtocolBinding + 8) = &BINDING_URL_TABLE::`vftable';
    *((_QWORD *)ProtocolBinding + 145) = 0;
    *((_QWORD *)ProtocolBinding + 146) = 0;
    *((_DWORD *)ProtocolBinding + 288) = 0;
    *(_DWORD *)ProtocolBinding = 1145979472;
    v9 = STRU::Copy((struct PROTOCOL_BINDING *)((char *)ProtocolBinding + 8), a2);
    if ( v9 < 0 )
    {
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\protocol_binding.cxx",
          547,
          "PROTOCOL_BINDING_LIST::AddBinding",
          v9,
          "Failed to initialize the protocol binding\r\n");
      PROTOCOL_BINDING::~PROTOCOL_BINDING(ProtocolBinding);
      operator delete(ProtocolBinding);
      return (unsigned int)v9;
    }
    v10 = (_QWORD *)((char *)this + 8);
    v11 = *((_QWORD *)this + 1);
    if ( *(PROTOCOL_BINDING_LIST **)(v11 + 8) != (PROTOCOL_BINDING_LIST *)((char *)this + 8) )
      __fastfail(3u);
    *((_QWORD *)ProtocolBinding + 145) = v11;
    *((_QWORD *)ProtocolBinding + 146) = v10;
    *(_QWORD *)(v11 + 8) = (char *)ProtocolBinding + 1160;
    *v10 = (char *)ProtocolBinding + 1160;
    ++*((_DWORD *)this + 6);
    goto LABEL_10;
  }
  v9 = -2147024888;
  if ( (g_dwDebugFlags & 0xF) != 0 )
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\protocol_binding.cxx",
      538,
      "PROTOCOL_BINDING_LIST::AddBinding",
      -2147024888,
      "Failed to allocated memory for protocol binding\r\n");
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180051254  push    rbx
0x180051256  push    rbp
0x180051257  push    rsi
0x180051258  push    rdi
0x180051259  sub     rsp, 38h
0x18005125d  mov     rbp, r8
0x180051260  mov     rdi, rdx
0x180051263  mov     rsi, rcx
0x180051266  call    ?FindProtocolBinding@PROTOCOL_BINDING_LIST@@QEAAPEAVPROTOCOL_BINDING@@PEBG@Z; PROTOCOL_BINDING_LIST::FindProtocolBinding(ushort const *)
0x18005126b  mov     rbx, rax
0x18005126e  test    rax, rax
0x180051271  jnz     loc_18005137B
0x180051277  mov     ecx, 498h; Size
0x18005127c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180051281  mov     rbx, rax
0x180051284  test    rax, rax
0x180051287  jz      loc_1800513AD
0x18005128d  lea     rcx, [rax+8]
0x180051291  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180051297  lea     rcx, [rbx+48h]; void *
0x18005129b  xor     edx, edx; Val
0x18005129d  mov     r8d, 418h; Size
0x1800512a3  mov     dword ptr [rcx+418h], 0
0x1800512ad  call    memset_0
0x1800512b2  mov     dword ptr [rbx+478h], 0
0x1800512bc  lea     rax, ??_7BINDING_URL_TABLE@@6B@; const BINDING_URL_TABLE::`vftable'
0x1800512c3  mov     [rbx+40h], rax
0x1800512c7  lea     rcx, [rbx+8]
0x1800512cb  mov     rdx, rdi
0x1800512ce  mov     qword ptr [rbx+488h], 0
0x1800512d9  mov     qword ptr [rbx+490h], 0
0x1800512e4  mov     dword ptr [rbx+480h], 0
0x1800512ee  mov     dword ptr [rbx], 444E4250h
0x1800512f4  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800512fa  mov     edi, eax
0x1800512fc  test    eax, eax
0x1800512fe  jns     short loc_18005134F
0x180051300  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180051307  jz      short loc_18005133A
0x180051309  mov     rcx, cs:g_pDebug
0x180051310  lea     rax, aFailedToInitia_5; "Failed to initialize the protocol bindi"...
0x180051317  mov     [rsp+58h+var_30], rax
0x18005131c  lea     r9, aProtocolBindin; "PROTOCOL_BINDING_LIST::AddBinding"
0x180051323  mov     r8d, 223h
0x180051329  mov     [rsp+58h+var_38], edi
0x18005132d  lea     rdx, aServercommonIn_25; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180051334  call    cs:__imp_PuDbgPrintError
0x18005133a  mov     rcx, rbx; this
0x18005133d  call    ??1PROTOCOL_BINDING@@QEAA@XZ; PROTOCOL_BINDING::~PROTOCOL_BINDING(void)
0x180051342  mov     rcx, rbx; Block
0x180051345  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18005134a  jmp     loc_1800513F5
0x18005134f  lea     rcx, [rsi+8]
0x180051353  mov     rdx, [rcx]
0x180051356  cmp     [rdx+8], rcx
0x18005135a  jz      short loc_180051363
0x18005135c  mov     ecx, 3
0x180051361  int     29h; Win8: RtlFailFast(ecx)
0x180051363  lea     rax, [rbx+488h]
0x18005136a  mov     [rax], rdx
0x18005136d  mov     [rax+8], rcx
0x180051371  mov     [rdx+8], rax
0x180051375  mov     [rcx], rax
0x180051378  inc     dword ptr [rsi+18h]
0x18005137b  mov     rdx, rbp; unsigned __int16 *
0x18005137e  mov     rcx, rbx; this
0x180051381  call    ?AddBinding@PROTOCOL_BINDING@@QEAAJPEBG@Z; PROTOCOL_BINDING::AddBinding(ushort const *)
0x180051386  mov     edi, eax
0x180051388  test    eax, eax
0x18005138a  jns     short loc_1800513F2
0x18005138c  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180051393  jz      short loc_1800513F5
0x180051395  lea     rax, aFailedToAddThe; "Failed to add the binding to the protoc"...
0x18005139c  mov     r8d, 237h
0x1800513a2  mov     [rsp+58h+var_30], rax
0x1800513a7  mov     [rsp+58h+var_38], edi
0x1800513ab  jmp     short loc_1800513D5
0x1800513ad  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800513b4  mov     edi, 80070008h
0x1800513b9  jz      short loc_1800513F5
0x1800513bb  lea     rax, aFailedToAlloca_2; "Failed to allocated memory for protocol"...
0x1800513c2  mov     r8d, 21Ah
0x1800513c8  mov     [rsp+58h+var_30], rax
0x1800513cd  mov     [rsp+58h+var_38], 80070008h
0x1800513d5  mov     rcx, cs:g_pDebug
0x1800513dc  lea     r9, aProtocolBindin; "PROTOCOL_BINDING_LIST::AddBinding"
0x1800513e3  lea     rdx, aServercommonIn_25; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800513ea  call    cs:__imp_PuDbgPrintError
0x1800513f0  jmp     short loc_1800513F5
0x1800513f2  inc     dword ptr [rsi+1Ch]
0x1800513f5  mov     eax, edi
0x1800513f7  add     rsp, 38h
0x1800513fb  pop     rdi
0x1800513fc  pop     rsi
0x1800513fd  pop     rbp
0x1800513fe  pop     rbx
0x1800513ff  retn
```
