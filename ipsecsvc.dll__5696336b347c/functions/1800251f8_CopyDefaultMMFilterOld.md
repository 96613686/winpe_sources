# CopyDefaultMMFilterOld

- ea: `0x1800251f8`
- end: `0x18002530d`
- name: `CopyDefaultMMFilterOld`
- size: `277`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800255e0`

## callees

- `0x18000e510`
- `0x1800173d0`
- `0x1800251f8`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x18002521c`
- `RPCRT4!UuidCreate` at `0x18002521c`

## pseudocode

```c
__int64 __fastcall CopyDefaultMMFilterOld(__int64 a1)
{
  _OWORD *v1; // rsi
  _OWORD *v3; // rbp
  RPC_STATUS v4; // eax
  unsigned int v5; // edi
  _QWORD *v6; // rcx
  __int64 v7; // rdx

  v1 = (_OWORD *)gpIniDefaultMMPolicy;
  v3 = (_OWORD *)gpIniDefaultMMAuthMethods;
  *(_DWORD *)a1 = 2;
  v4 = UuidCreate((UUID *)(a1 + 4));
  if ( !v4 || v4 == 1824 )
  {
    v5 = CopyName(L"0");
    if ( !v5 )
    {
      *(_DWORD *)(a1 + 40) = 3;
      *(_DWORD *)(a1 + 32) = 1;
      *(_DWORD *)(a1 + 36) = 1;
      *(_QWORD *)(a1 + 48) = 8;
      *(_DWORD *)(a1 + 56) = 0;
      *(_QWORD *)(a1 + 64) = 0;
      *(_QWORD *)(a1 + 80) = 8;
      *(_DWORD *)(a1 + 88) = 0;
      *(_QWORD *)(a1 + 96) = 0;
      *(_QWORD *)(a1 + 112) = 0;
      *(_OWORD *)(a1 + 120) = *v3;
      *(_OWORD *)(a1 + 136) = *v1;
      return v5;
    }
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v7 = 73;
      goto LABEL_6;
    }
  }
  else
  {
    v5 = 1726;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v7 = 72;
LABEL_6:
      WPP_SF_d(v6[2], v7, WPP_3e4f3b06ae6c3f7ee57f4df714640ff4_Traceguids, v5);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x1800251f8  push    rbx
0x1800251fa  push    rbp
0x1800251fb  push    rsi
0x1800251fc  push    rdi
0x1800251fd  sub     rsp, 28h
0x180025201  mov     rsi, cs:gpIniDefaultMMPolicy
0x180025208  mov     rbx, rcx
0x18002520b  mov     rbp, cs:gpIniDefaultMMAuthMethods
0x180025212  mov     dword ptr [rcx], 2
0x180025218  add     rcx, 4; Uuid
0x18002521c  call    cs:__imp_UuidCreate
0x180025222  test    eax, eax
0x180025224  jz      short loc_180025270
0x180025226  cmp     eax, 720h
0x18002522b  jz      short loc_180025270
0x18002522d  mov     edi, 6BEh
0x180025232  mov     rcx, cs:WPP_GLOBAL_Control
0x180025239  lea     rax, WPP_GLOBAL_Control
0x180025240  cmp     rcx, rax
0x180025243  jz      loc_180025302
0x180025249  test    byte ptr [rcx+1Ch], 10h
0x18002524d  jz      loc_180025302
0x180025253  mov     edx, 48h ; 'H'
0x180025258  mov     rcx, [rcx+10h]
0x18002525c  lea     r8, WPP_3e4f3b06ae6c3f7ee57f4df714640ff4_Traceguids
0x180025263  mov     r9d, edi
0x180025266  call    WPP_SF_d
0x18002526b  jmp     loc_180025302
0x180025270  lea     rdx, [rbx+18h]
0x180025274  lea     rcx, a0; "0"
0x18002527b  call    CopyName
0x180025280  mov     edi, eax
0x180025282  test    eax, eax
0x180025284  jz      short loc_1800252A6
0x180025286  mov     rcx, cs:WPP_GLOBAL_Control
0x18002528d  lea     rax, WPP_GLOBAL_Control
0x180025294  cmp     rcx, rax
0x180025297  jz      short loc_180025302
0x180025299  test    byte ptr [rcx+1Ch], 10h
0x18002529d  jz      short loc_180025302
0x18002529f  mov     edx, 49h ; 'I'
0x1800252a4  jmp     short loc_180025258
0x1800252a6  mov     eax, 1
0x1800252ab  mov     dword ptr [rbx+28h], 3
0x1800252b2  mov     [rbx+20h], eax
0x1800252b5  mov     [rbx+24h], eax
0x1800252b8  mov     qword ptr [rbx+30h], 8
0x1800252c0  mov     dword ptr [rbx+38h], 0
0x1800252c7  mov     qword ptr [rbx+40h], 0
0x1800252cf  mov     qword ptr [rbx+50h], 8
0x1800252d7  mov     dword ptr [rbx+58h], 0
0x1800252de  mov     qword ptr [rbx+60h], 0
0x1800252e6  mov     qword ptr [rbx+70h], 0
0x1800252ee  movups  xmm0, xmmword ptr [rbp+0]
0x1800252f2  movdqu  xmmword ptr [rbx+78h], xmm0
0x1800252f7  movups  xmm1, xmmword ptr [rsi]
0x1800252fa  movdqu  xmmword ptr [rbx+88h], xmm1
0x180025302  mov     eax, edi
0x180025304  add     rsp, 28h
0x180025308  pop     rdi
0x180025309  pop     rsi
0x18002530a  pop     rbp
0x18002530b  pop     rbx
0x18002530c  retn
```
