# MRxDAVFsCtlContinuation

- ea: `0x1400115f0`
- end: `0x1400116ef`
- name: `MRxDAVFsCtlContinuation`
- size: `255`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x14000163c`
- `0x140001680`
- `0x140001b64`
- `0x1400115f0`
- `0x1400287f4`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x14001161f`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001165b`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400116bc`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001161f`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001165b`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400116bc`

## pseudocode

```c
__int64 __fastcall MRxDAVFsCtlContinuation(__int64 a1, __int64 a2)
{
  __int64 v4; // rbx
  HANDLE CurrentThreadId; // rax
  __int64 v6; // rbx
  HANDLE v7; // rax
  unsigned int v8; // edi
  __int64 v9; // rbx
  HANDLE v10; // rax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
    {
      v4 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      CurrentThreadId = PsGetCurrentThreadId();
      WPP_SF_q(v4, 24, WPP_75f6759884be3ad3b7c5c9a1d3975786_Traceguids, CurrentThreadId);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
    {
      v6 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v7 = PsGetCurrentThreadId();
      WPP_SF_qqq(v6, 25, WPP_75f6759884be3ad3b7c5c9a1d3975786_Traceguids, v7, a1, a2);
    }
  }
  v8 = UMRxSubmitAsyncEngUserModeRequest(
         a1,
         a2,
         MRxDAVFormatUserModeFsCtlRequest,
         MRxDAVPrecompleteUserModeFsCtlRequest);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
  {
    v9 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v10 = PsGetCurrentThreadId();
    WPP_SF_qD(v9, 26, WPP_75f6759884be3ad3b7c5c9a1d3975786_Traceguids, v10, v8);
  }
  return v8;
}

```

## disassembly

```asm
0x1400115f0  push    rbx
0x1400115f2  push    rbp
0x1400115f3  push    rsi
0x1400115f4  push    rdi
0x1400115f5  sub     rsp, 38h
0x1400115f9  mov     rdi, rdx
0x1400115fc  mov     rsi, rcx
0x1400115ff  mov     rbx, cs:WPP_GLOBAL_Control
0x140011606  lea     rbp, WPP_GLOBAL_Control
0x14001160d  cmp     rbx, rbp
0x140011610  jz      short loc_140011688
0x140011612  test    dword ptr [rbx+2Ch], 4000h
0x140011619  jz      short loc_140011642
0x14001161b  mov     rbx, [rbx+18h]
0x14001161f  call    cs:__imp_PsGetCurrentThreadId
0x140011626  nop     dword ptr [rax+rax+00h]
0x14001162b  mov     edx, 18h
0x140011630  lea     r8, WPP_75f6759884be3ad3b7c5c9a1d3975786_Traceguids
0x140011637  mov     r9, rax
0x14001163a  mov     rcx, rbx
0x14001163d  call    WPP_SF_q
0x140011642  mov     rbx, cs:WPP_GLOBAL_Control
0x140011649  cmp     rbx, rbp
0x14001164c  jz      short loc_140011688
0x14001164e  test    dword ptr [rbx+2Ch], 2000h
0x140011655  jz      short loc_140011688
0x140011657  mov     rbx, [rbx+18h]
0x14001165b  call    cs:__imp_PsGetCurrentThreadId
0x140011662  nop     dword ptr [rax+rax+00h]
0x140011667  mov     edx, 19h
0x14001166c  mov     [rsp+58h+var_30], rdi
0x140011671  mov     r9, rax
0x140011674  mov     [rsp+58h+var_38], rsi
0x140011679  lea     r8, WPP_75f6759884be3ad3b7c5c9a1d3975786_Traceguids
0x140011680  mov     rcx, rbx
0x140011683  call    WPP_SF_qqq
0x140011688  lea     r9, MRxDAVPrecompleteUserModeFsCtlRequest
0x14001168f  mov     rdx, rdi
0x140011692  lea     r8, MRxDAVFormatUserModeFsCtlRequest
0x140011699  mov     rcx, rsi
0x14001169c  call    UMRxSubmitAsyncEngUserModeRequest
0x1400116a1  mov     edi, eax
0x1400116a3  mov     rbx, cs:WPP_GLOBAL_Control
0x1400116aa  cmp     rbx, rbp
0x1400116ad  jz      short loc_1400116E3
0x1400116af  test    dword ptr [rbx+2Ch], 4000h
0x1400116b6  jz      short loc_1400116E3
0x1400116b8  mov     rbx, [rbx+18h]
0x1400116bc  call    cs:__imp_PsGetCurrentThreadId
0x1400116c3  nop     dword ptr [rax+rax+00h]
0x1400116c8  mov     edx, 1Ah
0x1400116cd  mov     dword ptr [rsp+58h+var_38], edi
0x1400116d1  mov     r9, rax
0x1400116d4  lea     r8, WPP_75f6759884be3ad3b7c5c9a1d3975786_Traceguids
0x1400116db  mov     rcx, rbx
0x1400116de  call    WPP_SF_qD
0x1400116e3  mov     eax, edi
0x1400116e5  add     rsp, 38h
0x1400116e9  pop     rdi
0x1400116ea  pop     rsi
0x1400116eb  pop     rbp
0x1400116ec  pop     rbx
0x1400116ed  retn
```
