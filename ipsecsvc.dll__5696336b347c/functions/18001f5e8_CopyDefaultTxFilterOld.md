# CopyDefaultTxFilterOld

- ea: `0x18001f5e8`
- end: `0x18001f72e`
- name: `CopyDefaultTxFilterOld`
- size: `326`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18001f930`

## callees

- `0x18000e510`
- `0x1800173d0`
- `0x18001f5e8`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x18001f60b`
- `RPCRT4!UuidCreate` at `0x18001f60b`

## pseudocode

```c
__int64 __fastcall CopyDefaultTxFilterOld(__int64 a1)
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
      *(_WORD *)(a1 + 124) = 0;
      *(_WORD *)(a1 + 132) = 0;
      *(_DWORD *)(a1 + 36) = 1;
      *(_DWORD *)(a1 + 136) = 3;
      *(_QWORD *)(a1 + 140) = 3;
      *(_QWORD *)(a1 + 48) = 8;
      *(_DWORD *)(a1 + 56) = 0;
      *(_QWORD *)(a1 + 64) = 0;
      *(_QWORD *)(a1 + 80) = 8;
      *(_DWORD *)(a1 + 88) = 0;
      *(_QWORD *)(a1 + 96) = 0;
      *(_QWORD *)(a1 + 112) = 1;
      *(_DWORD *)(a1 + 120) = 1;
      *(_DWORD *)(a1 + 128) = 1;
      *(_DWORD *)(a1 + 148) = 0;
      *(_OWORD *)(a1 + 152) = *v1;
      return v4;
    }
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v6 = 83;
      goto LABEL_6;
    }
  }
  else
  {
    v4 = 1726;
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v6 = 82;
LABEL_6:
      WPP_SF_d(v5[2], v6, WPP_9e5bd0d0d2233fe69730d263c30676fb_Traceguids, v4);
    }
  }
  return v4;
}

```

## disassembly

```asm
0x18001f5e8  mov     [rsp+arg_0], rbx
0x18001f5ed  mov     [rsp+arg_8], rsi
0x18001f5f2  push    rdi
0x18001f5f3  sub     rsp, 20h
0x18001f5f7  mov     rsi, cs:gpIniDefaultQMPolicy
0x18001f5fe  mov     rbx, rcx
0x18001f601  mov     dword ptr [rcx], 2
0x18001f607  add     rcx, 4; Uuid
0x18001f60b  call    cs:__imp_UuidCreate
0x18001f611  test    eax, eax
0x18001f613  jz      short loc_18001F65F
0x18001f615  cmp     eax, 720h
0x18001f61a  jz      short loc_18001F65F
0x18001f61c  mov     edi, 6BEh
0x18001f621  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f628  lea     rax, WPP_GLOBAL_Control
0x18001f62f  cmp     rcx, rax
0x18001f632  jz      loc_18001F71C
0x18001f638  test    byte ptr [rcx+1Ch], 10h
0x18001f63c  jz      loc_18001F71C
0x18001f642  mov     edx, 52h ; 'R'
0x18001f647  mov     rcx, [rcx+10h]
0x18001f64b  lea     r8, WPP_9e5bd0d0d2233fe69730d263c30676fb_Traceguids
0x18001f652  mov     r9d, edi
0x18001f655  call    WPP_SF_d
0x18001f65a  jmp     loc_18001F71C
0x18001f65f  lea     rdx, [rbx+18h]
0x18001f663  lea     rcx, a0; "0"
0x18001f66a  call    CopyName
0x18001f66f  mov     edi, eax
0x18001f671  test    eax, eax
0x18001f673  jz      short loc_18001F69D
0x18001f675  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f67c  lea     rax, WPP_GLOBAL_Control
0x18001f683  cmp     rcx, rax
0x18001f686  jz      loc_18001F71C
0x18001f68c  test    byte ptr [rcx+1Ch], 10h
0x18001f690  jz      loc_18001F71C
0x18001f696  mov     edx, 53h ; 'S'
0x18001f69b  jmp     short loc_18001F647
0x18001f69d  mov     ecx, 1
0x18001f6a2  mov     dword ptr [rbx+28h], 2
0x18001f6a9  xor     eax, eax
0x18001f6ab  mov     [rbx+20h], ecx
0x18001f6ae  mov     [rbx+7Ch], ax
0x18001f6b2  mov     [rbx+84h], ax
0x18001f6b9  lea     eax, [rcx+2]
0x18001f6bc  mov     [rbx+24h], ecx
0x18001f6bf  mov     [rbx+88h], eax
0x18001f6c5  mov     [rbx+8Ch], rax
0x18001f6cc  mov     qword ptr [rbx+30h], 8
0x18001f6d4  mov     dword ptr [rbx+38h], 0
0x18001f6db  mov     qword ptr [rbx+40h], 0
0x18001f6e3  mov     qword ptr [rbx+50h], 8
0x18001f6eb  mov     dword ptr [rbx+58h], 0
0x18001f6f2  mov     qword ptr [rbx+60h], 0
0x18001f6fa  mov     [rbx+70h], rcx
0x18001f6fe  mov     [rbx+78h], ecx
0x18001f701  mov     [rbx+80h], ecx
0x18001f707  mov     dword ptr [rbx+94h], 0
0x18001f711  movups  xmm0, xmmword ptr [rsi]
0x18001f714  movdqu  xmmword ptr [rbx+98h], xmm0
0x18001f71c  mov     rbx, [rsp+28h+arg_0]
0x18001f721  mov     eax, edi
0x18001f723  mov     rsi, [rsp+28h+arg_8]
0x18001f728  add     rsp, 20h
0x18001f72c  pop     rdi
0x18001f72d  retn
```
