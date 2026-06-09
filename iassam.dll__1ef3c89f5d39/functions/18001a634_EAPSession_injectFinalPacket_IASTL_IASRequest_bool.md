# EAPSession::injectFinalPacket(IASTL::IASRequest &,bool)

- ea: `0x18001a634`
- end: `0x18001a730`
- name: `?injectFinalPacket@EAPSession@@QEAAXAEAVIASRequest@IASTL@@_N@Z`
- size: `252`
- prototype: `void(EAPSession *__hidden this, struct IASTL::IASRequest *, bool)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800179e0`

## callees

- `0x18000c500`
- `0x18000c808`
- `0x180018b10`
- `0x180018de4`
- `0x18001a634`
- `0x1800254a0`
- `0x18002e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a666`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a666`

## pseudocode

```c
void __fastcall EAPSession::injectFinalPacket(EAPSession *this, struct IASTL::IASRequest *a2, unsigned __int8 a3)
{
  unsigned int v4; // ebp
  const struct _PPP_EAP_PACKET **v6; // rdi
  void *v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rdx
  int v10; // ebx
  int v11; // [rsp+60h] [rbp+8h] BYREF
  struct _EAP_ERROR *v12; // [rsp+78h] [rbp+20h] BYREF

  v4 = a3;
  if ( *((_DWORD *)this + 86) == 2 )
  {
    v6 = (const struct _PPP_EAP_PACKET **)((char *)this + 192);
    v7 = (void *)*((_QWORD *)this + 24);
    if ( v7 )
      CoTaskMemFree(v7);
    v8 = *((_QWORD *)this + 44);
    v9 = *((unsigned int *)this + 87);
    v12 = 0;
    v11 = 0;
    v10 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, int *, const struct _PPP_EAP_PACKET **, struct _EAP_ERROR **))(*(_QWORD *)v8 + 96LL))(
            v8,
            v9,
            v4,
            &v11,
            v6,
            &v12);
    if ( v10 < 0 )
    {
      FreeEAPError(v12);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WppDbgPrint("EapHostAuthenticatorGetFinalPacket failed with error: %d");
        WPP_SF_sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_69033002015f3c629418a4473ed337be_Traceguids);
      }
      _com_issue_error(v10);
    }
    InjectPacket(a2, *v6, 7u);
  }
}

```

## disassembly

```asm
0x18001a634  mov     [rsp+arg_8], rbx
0x18001a639  push    rbp
0x18001a63a  push    rsi
0x18001a63b  push    rdi
0x18001a63c  sub     rsp, 40h
0x18001a640  cmp     dword ptr [rcx+158h], 2
0x18001a647  mov     rsi, rdx
0x18001a64a  movzx   ebp, r8b
0x18001a64e  mov     rbx, rcx
0x18001a651  jnz     loc_18001A723
0x18001a657  lea     rdi, [rcx+0C0h]
0x18001a65e  mov     rcx, [rdi]; pv
0x18001a661  test    rcx, rcx
0x18001a664  jz      short loc_18001A66C
0x18001a666  call    cs:__imp_CoTaskMemFree
0x18001a66c  mov     rcx, [rbx+160h]
0x18001a673  lea     rdx, [rsp+58h+arg_18]
0x18001a678  mov     [rsp+58h+var_30], rdx
0x18001a67d  lea     r9, [rsp+58h+arg_0]
0x18001a682  mov     edx, [rbx+15Ch]
0x18001a688  mov     r8d, ebp
0x18001a68b  mov     [rsp+58h+arg_18], 0
0x18001a694  mov     [rsp+58h+arg_0], 0
0x18001a69c  mov     rax, [rcx]
0x18001a69f  mov     [rsp+58h+var_38], rdi
0x18001a6a4  mov     rax, [rax+60h]
0x18001a6a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a6ad  mov     ebx, eax
0x18001a6af  test    eax, eax
0x18001a6b1  jns     short loc_18001A712
0x18001a6b3  mov     rcx, [rsp+58h+arg_18]; struct _EAP_ERROR *
0x18001a6b8  call    ?FreeEAPError@@YAXPEAU_EAP_ERROR@@@Z; FreeEAPError(_EAP_ERROR *)
0x18001a6bd  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a6c4  lea     rax, WPP_GLOBAL_Control
0x18001a6cb  cmp     rcx, rax
0x18001a6ce  jz      short loc_18001A70A
0x18001a6d0  cmp     byte ptr [rcx+19h], 2
0x18001a6d4  jb      short loc_18001A70A
0x18001a6d6  test    byte ptr [rcx+1Ch], 4
0x18001a6da  jz      short loc_18001A70A
0x18001a6dc  mov     edx, ebx
0x18001a6de  lea     rcx, aEaphostauthent_1; "EapHostAuthenticatorGetFinalPacket fail"...
0x18001a6e5  call    WppDbgPrint
0x18001a6ea  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a6f1  lea     r8, WPP_69033002015f3c629418a4473ed337be_Traceguids
0x18001a6f8  mov     edx, 29h ; ')'
0x18001a6fd  mov     dword ptr [rsp+58h+var_38], ebx
0x18001a701  mov     rcx, [rcx+10h]
0x18001a705  call    WPP_SF_sd
0x18001a70a  mov     ecx, ebx; int
0x18001a70c  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18001a712  mov     rdx, [rdi]; struct _PPP_EAP_PACKET *
0x18001a715  mov     r8d, 7; unsigned int
0x18001a71b  mov     rcx, rsi; struct IASTL::IASRequest *
0x18001a71e  call    ?InjectPacket@@YAXAEAVIASRequest@IASTL@@AEBU_PPP_EAP_PACKET@@K@Z; InjectPacket(IASTL::IASRequest &,_PPP_EAP_PACKET const &,ulong)
0x18001a723  mov     rbx, [rsp+58h+arg_8]
0x18001a728  add     rsp, 40h
0x18001a72c  pop     rdi
0x18001a72d  pop     rsi
0x18001a72e  pop     rbp
0x18001a72f  retn
```
