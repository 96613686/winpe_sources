# NcaEvCollHttpProbeCollectWinHttpSessionInit(NCA_EVCOLL_PROBE_ *)

- ea: `0x1800111c8`
- end: `0x1800112a5`
- name: `?NcaEvCollHttpProbeCollectWinHttpSessionInit@@YAKPEAUNCA_EVCOLL_PROBE_@@@Z`
- size: `221`
- prototype: `__int64 __fastcall(struct NCA_EVCOLL_PROBE_ *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180001400`

## callees

- `0x180004f34`
- `0x1800111c8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011201`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011258`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011201`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011258`
- `WINHTTP!WinHttpConnect` at `0x180011243`
- `WINHTTP!WinHttpConnect` at `0x180011243`
- `WINHTTP!WinHttpOpen` at `0x1800111ec`
- `WINHTTP!WinHttpOpen` at `0x1800111ec`

## pseudocode

```c
__int64 __fastcall NcaEvCollHttpProbeCollectWinHttpSessionInit(struct NCA_EVCOLL_PROBE_ *a1)
{
  void *v2; // rax
  DWORD LastError; // ebx
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  HINTERNET v6; // rax

  v2 = WinHttpOpen(L"Client NCA", 0, 0, 0, 0x10000000u);
  *((_QWORD *)a1 + 5) = v2;
  if ( v2 )
  {
    LastError = 0;
    v6 = WinHttpConnect(v2, *((LPCWSTR *)a1 + 20), *((_WORD *)a1 + 46), 0);
    *((_QWORD *)a1 + 6) = v6;
    if ( !v6 )
    {
      LastError = GetLastError();
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v5 = 55;
        goto LABEL_9;
      }
    }
  }
  else
  {
    LastError = GetLastError();
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v5 = 54;
LABEL_9:
      WPP_SF_d(v4[2], v5, &WPP_40278bcc69653b1fe66ed785fbbec1d5_Traceguids, LastError);
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x1800111c8  mov     [rsp+arg_0], rbx
0x1800111cd  push    rdi
0x1800111ce  sub     rsp, 30h
0x1800111d2  mov     rdi, rcx
0x1800111d5  mov     [rsp+38h+dwFlags], 10000000h; dwFlags
0x1800111dd  lea     rcx, pszAgentW; "Client NCA"
0x1800111e4  xor     r9d, r9d; pszProxyBypassW
0x1800111e7  xor     r8d, r8d; pszProxyW
0x1800111ea  xor     edx, edx; dwAccessType
0x1800111ec  call    cs:__imp_WinHttpOpen
0x1800111f3  nop     dword ptr [rax+rax+00h]
0x1800111f8  mov     [rdi+28h], rax
0x1800111fc  test    rax, rax
0x1800111ff  jnz     short loc_18001122F
0x180011201  call    cs:__imp_GetLastError
0x180011208  nop     dword ptr [rax+rax+00h]
0x18001120d  mov     ebx, eax
0x18001120f  mov     rcx, cs:WPP_GLOBAL_Control
0x180011216  lea     rax, WPP_GLOBAL_Control
0x18001121d  cmp     rcx, rax
0x180011220  jz      short loc_180011297
0x180011222  test    byte ptr [rcx+1Ch], 1
0x180011226  jz      short loc_180011297
0x180011228  mov     edx, 36h ; '6'
0x18001122d  jmp     short loc_180011284
0x18001122f  movzx   r8d, word ptr [rdi+5Ch]; nServerPort
0x180011234  xor     r9d, r9d; dwReserved
0x180011237  mov     rdx, [rdi+0A0h]; pswzServerName
0x18001123e  mov     rcx, rax; hSession
0x180011241  xor     ebx, ebx
0x180011243  call    cs:__imp_WinHttpConnect
0x18001124a  nop     dword ptr [rax+rax+00h]
0x18001124f  mov     [rdi+30h], rax
0x180011253  test    rax, rax
0x180011256  jnz     short loc_180011297
0x180011258  call    cs:__imp_GetLastError
0x18001125f  nop     dword ptr [rax+rax+00h]
0x180011264  mov     ebx, eax
0x180011266  mov     rcx, cs:WPP_GLOBAL_Control
0x18001126d  lea     rax, WPP_GLOBAL_Control
0x180011274  cmp     rcx, rax
0x180011277  jz      short loc_180011297
0x180011279  test    byte ptr [rcx+1Ch], 1
0x18001127d  jz      short loc_180011297
0x18001127f  mov     edx, 37h ; '7'
0x180011284  mov     rcx, [rcx+10h]
0x180011288  lea     r8, WPP_40278bcc69653b1fe66ed785fbbec1d5_Traceguids
0x18001128f  mov     r9d, ebx
0x180011292  call    WPP_SF_d
0x180011297  mov     eax, ebx
0x180011299  mov     rbx, [rsp+38h+arg_0]
0x18001129e  add     rsp, 30h
0x1800112a2  pop     rdi
0x1800112a3  retn
```
