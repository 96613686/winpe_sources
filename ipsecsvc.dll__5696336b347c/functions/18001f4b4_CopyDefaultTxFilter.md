# CopyDefaultTxFilter

- ea: `0x18001f4b4`
- end: `0x18001f5e2`
- name: `CopyDefaultTxFilter`
- size: `302`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18001f740`

## callees

- `0x18000e510`
- `0x1800173d0`
- `0x18001f4b4`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x18001f4d7`
- `RPCRT4!UuidCreate` at `0x18001f4d7`

## pseudocode

```c
__int64 __fastcall CopyDefaultTxFilter(__int64 a1)
{
  _OWORD *v1; // rsi
  RPC_STATUS v3; // eax
  unsigned int v4; // edi
  _QWORD *v5; // rcx
  __int64 v6; // rdx

  v1 = (_OWORD *)gpIniDefaultQMPolicy;
  *(_DWORD *)a1 = 0;
  v3 = UuidCreate((UUID *)(a1 + 4));
  if ( !v3 || v3 == 1824 )
  {
    v4 = CopyName(L"0");
    if ( !v4 )
    {
      *(_QWORD *)(a1 + 56) = 0;
      *(_DWORD *)(a1 + 32) = 1;
      *(_DWORD *)(a1 + 36) = 1;
      *(_QWORD *)(a1 + 96) = 0;
      *(_QWORD *)(a1 + 128) = 1;
      *(_DWORD *)(a1 + 40) = 2;
      *(_DWORD *)(a1 + 48) = 2;
      *(_DWORD *)(a1 + 88) = 2;
      *(_WORD *)(a1 + 140) = 0;
      *(_WORD *)(a1 + 148) = 0;
      *(_DWORD *)(a1 + 152) = 3;
      *(_QWORD *)(a1 + 156) = 3;
      *(_DWORD *)(a1 + 136) = 1;
      *(_DWORD *)(a1 + 144) = 1;
      *(_DWORD *)(a1 + 164) = 0;
      *(_OWORD *)(a1 + 168) = *v1;
      return v4;
    }
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v6 = 81;
      goto LABEL_6;
    }
  }
  else
  {
    v4 = 1726;
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v6 = 80;
LABEL_6:
      WPP_SF_d(v5[2], v6, WPP_9e5bd0d0d2233fe69730d263c30676fb_Traceguids, v4);
    }
  }
  return v4;
}

```

## disassembly

```asm
0x18001f4b4  mov     [rsp+arg_0], rbx
0x18001f4b9  mov     [rsp+arg_8], rsi
0x18001f4be  push    rdi
0x18001f4bf  sub     rsp, 20h
0x18001f4c3  mov     rsi, cs:gpIniDefaultQMPolicy
0x18001f4ca  mov     rbx, rcx
0x18001f4cd  mov     dword ptr [rcx], 0
0x18001f4d3  add     rcx, 4; Uuid
0x18001f4d7  call    cs:__imp_UuidCreate
0x18001f4dd  test    eax, eax
0x18001f4df  jz      short loc_18001F52B
0x18001f4e1  cmp     eax, 720h
0x18001f4e6  jz      short loc_18001F52B
0x18001f4e8  mov     edi, 6BEh
0x18001f4ed  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f4f4  lea     rax, WPP_GLOBAL_Control
0x18001f4fb  cmp     rcx, rax
0x18001f4fe  jz      loc_18001F5D0
0x18001f504  test    byte ptr [rcx+1Ch], 10h
0x18001f508  jz      loc_18001F5D0
0x18001f50e  mov     edx, 50h ; 'P'
0x18001f513  mov     rcx, [rcx+10h]
0x18001f517  lea     r8, WPP_9e5bd0d0d2233fe69730d263c30676fb_Traceguids
0x18001f51e  mov     r9d, edi
0x18001f521  call    WPP_SF_d
0x18001f526  jmp     loc_18001F5D0
0x18001f52b  lea     rdx, [rbx+18h]
0x18001f52f  lea     rcx, a0; "0"
0x18001f536  call    CopyName
0x18001f53b  mov     edi, eax
0x18001f53d  test    eax, eax
0x18001f53f  jz      short loc_18001F561
0x18001f541  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f548  lea     rax, WPP_GLOBAL_Control
0x18001f54f  cmp     rcx, rax
0x18001f552  jz      short loc_18001F5D0
0x18001f554  test    byte ptr [rcx+1Ch], 10h
0x18001f558  jz      short loc_18001F5D0
0x18001f55a  mov     edx, 51h ; 'Q'
0x18001f55f  jmp     short loc_18001F513
0x18001f561  mov     ecx, 1
0x18001f566  mov     qword ptr [rbx+38h], 0
0x18001f56e  mov     [rbx+20h], ecx
0x18001f571  mov     [rbx+24h], ecx
0x18001f574  mov     qword ptr [rbx+60h], 0
0x18001f57c  lea     eax, [rcx+1]
0x18001f57f  mov     [rbx+80h], rcx
0x18001f586  mov     [rbx+28h], eax
0x18001f589  mov     [rbx+30h], eax
0x18001f58c  mov     [rbx+58h], eax
0x18001f58f  xor     eax, eax
0x18001f591  mov     [rbx+8Ch], ax
0x18001f598  mov     [rbx+94h], ax
0x18001f59f  lea     eax, [rcx+2]
0x18001f5a2  mov     [rbx+98h], eax
0x18001f5a8  mov     [rbx+9Ch], rax
0x18001f5af  mov     [rbx+88h], ecx
0x18001f5b5  mov     [rbx+90h], ecx
0x18001f5bb  mov     dword ptr [rbx+0A4h], 0
0x18001f5c5  movups  xmm0, xmmword ptr [rsi]
0x18001f5c8  movdqu  xmmword ptr [rbx+0A8h], xmm0
0x18001f5d0  mov     rbx, [rsp+28h+arg_0]
0x18001f5d5  mov     eax, edi
0x18001f5d7  mov     rsi, [rsp+28h+arg_8]
0x18001f5dc  add     rsp, 20h
0x18001f5e0  pop     rdi
0x18001f5e1  retn
```
