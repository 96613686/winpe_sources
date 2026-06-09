# CopyDefaultTnFilter

- ea: `0x180033b40`
- end: `0x180033c93`
- name: `CopyDefaultTnFilter`
- size: `339`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180033c9c`

## callees

- `0x18000e510`
- `0x1800173d0`
- `0x180033b40`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x180033b5d`
- `RPCRT4!UuidCreate` at `0x180033b5d`

## pseudocode

```c
__int64 __fastcall CopyDefaultTnFilter(__int64 a1)
{
  _OWORD *v1; // rsi
  RPC_STATUS v3; // eax
  unsigned int v4; // edi
  _QWORD *v5; // rcx
  __int64 v6; // rdx

  v1 = (_OWORD *)gpIniDefaultQMPolicy;
  *(_DWORD *)a1 = 2;
  v3 = UuidCreate((UUID *)(a1 + 4));
  if ( !v3 || v3 == 1824 )
  {
    v4 = CopyName(L"0");
    if ( !v4 )
    {
      *(_DWORD *)(a1 + 40) = 2;
      *(_DWORD *)(a1 + 32) = 1;
      *(_DWORD *)(a1 + 36) = 1;
      *(_QWORD *)(a1 + 48) = 8;
      *(_DWORD *)(a1 + 56) = 0;
      *(_DWORD *)(a1 + 200) = 3;
      *(_QWORD *)(a1 + 204) = 3;
      *(_QWORD *)(a1 + 64) = 0;
      *(_QWORD *)(a1 + 80) = 8;
      *(_DWORD *)(a1 + 88) = 0;
      *(_QWORD *)(a1 + 96) = 0;
      *(_QWORD *)(a1 + 136) = 8;
      *(_DWORD *)(a1 + 144) = 0;
      *(_QWORD *)(a1 + 152) = 0;
      *(_QWORD *)(a1 + 168) = 8;
      *(_DWORD *)(a1 + 176) = 0;
      *(_QWORD *)(a1 + 184) = 0;
      *(_QWORD *)(a1 + 112) = 1;
      *(_DWORD *)(a1 + 120) = 1;
      *(_WORD *)(a1 + 124) = 0;
      *(_DWORD *)(a1 + 128) = 1;
      *(_WORD *)(a1 + 132) = 0;
      *(_DWORD *)(a1 + 212) = 0;
      *(_OWORD *)(a1 + 216) = *v1;
      return v4;
    }
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v6 = 49;
      goto LABEL_6;
    }
  }
  else
  {
    v4 = 1726;
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v6 = 48;
LABEL_6:
      WPP_SF_d(v5[2], v6, WPP_57823a57097e38bdba1c3f07a42a9825_Traceguids, v4);
    }
  }
  return v4;
}

```

## disassembly

```asm
0x180033b40  push    rbx
0x180033b42  push    rbp
0x180033b43  push    rsi
0x180033b44  push    rdi
0x180033b45  sub     rsp, 28h
0x180033b49  mov     rsi, cs:gpIniDefaultQMPolicy
0x180033b50  mov     rbx, rcx
0x180033b53  mov     dword ptr [rcx], 2
0x180033b59  add     rcx, 4; Uuid
0x180033b5d  call    cs:__imp_UuidCreate
0x180033b63  xor     ebp, ebp
0x180033b65  test    eax, eax
0x180033b67  jz      short loc_180033BB1
0x180033b69  cmp     eax, 720h
0x180033b6e  jz      short loc_180033BB1
0x180033b70  mov     edi, 6BEh
0x180033b75  mov     rcx, cs:WPP_GLOBAL_Control
0x180033b7c  lea     rax, WPP_GLOBAL_Control
0x180033b83  cmp     rcx, rax
0x180033b86  jz      loc_180033C88
0x180033b8c  test    byte ptr [rcx+1Ch], 10h
0x180033b90  jz      loc_180033C88
0x180033b96  lea     edx, [rbp+30h]
0x180033b99  mov     rcx, [rcx+10h]
0x180033b9d  lea     r8, WPP_57823a57097e38bdba1c3f07a42a9825_Traceguids
0x180033ba4  mov     r9d, edi
0x180033ba7  call    WPP_SF_d
0x180033bac  jmp     loc_180033C88
0x180033bb1  lea     rdx, [rbx+18h]
0x180033bb5  lea     rcx, a0; "0"
0x180033bbc  call    CopyName
0x180033bc1  mov     edi, eax
0x180033bc3  test    eax, eax
0x180033bc5  jz      short loc_180033BEF
0x180033bc7  mov     rcx, cs:WPP_GLOBAL_Control
0x180033bce  lea     rax, WPP_GLOBAL_Control
0x180033bd5  cmp     rcx, rax
0x180033bd8  jz      loc_180033C88
0x180033bde  test    byte ptr [rcx+1Ch], 10h
0x180033be2  jz      loc_180033C88
0x180033be8  mov     edx, 31h ; '1'
0x180033bed  jmp     short loc_180033B99
0x180033bef  mov     ecx, 1
0x180033bf4  mov     dword ptr [rbx+28h], 2
0x180033bfb  mov     [rbx+20h], ecx
0x180033bfe  mov     [rbx+24h], ecx
0x180033c01  mov     qword ptr [rbx+30h], 8
0x180033c09  lea     eax, [rcx+2]
0x180033c0c  mov     [rbx+38h], ebp
0x180033c0f  mov     [rbx+0C8h], eax
0x180033c15  mov     [rbx+0CCh], rax
0x180033c1c  mov     [rbx+40h], rbp
0x180033c20  mov     qword ptr [rbx+50h], 8
0x180033c28  mov     [rbx+58h], ebp
0x180033c2b  mov     [rbx+60h], rbp
0x180033c2f  mov     qword ptr [rbx+88h], 8
0x180033c3a  mov     [rbx+90h], ebp
0x180033c40  mov     [rbx+98h], rbp
0x180033c47  mov     qword ptr [rbx+0A8h], 8
0x180033c52  mov     [rbx+0B0h], ebp
0x180033c58  mov     [rbx+0B8h], rbp
0x180033c5f  mov     [rbx+70h], rcx
0x180033c63  mov     [rbx+78h], ecx
0x180033c66  mov     [rbx+7Ch], bp
0x180033c6a  mov     [rbx+80h], ecx
0x180033c70  mov     [rbx+84h], bp
0x180033c77  mov     [rbx+0D4h], ebp
0x180033c7d  movups  xmm0, xmmword ptr [rsi]
0x180033c80  movdqu  xmmword ptr [rbx+0D8h], xmm0
0x180033c88  mov     eax, edi
0x180033c8a  add     rsp, 28h
0x180033c8e  pop     rdi
0x180033c8f  pop     rsi
0x180033c90  pop     rbp
0x180033c91  pop     rbx
0x180033c92  retn
```
