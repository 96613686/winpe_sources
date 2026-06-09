# DwmpCreateAnimationClock

- ea: `0x180011240`
- end: `0x1800112b3`
- name: `DwmpCreateAnimationClock`
- size: `115`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180016644`

## callees

- `0x18000352c`
- `0x18000925c`
- `0x180011240`

## pseudocode

```c
__int64 __fastcall DwmpCreateAnimationClock(CApiPortClient *a1, int a2)
{
  __int128 v2; // xmm0
  int v3; // eax
  unsigned int v4; // ebx
  int v6; // [rsp+30h] [rbp-28h] BYREF
  __int128 v7; // [rsp+34h] [rbp-24h]
  int v8; // [rsp+44h] [rbp-14h]
  int v9; // [rsp+68h] [rbp+10h] BYREF

  v2 = *(_OWORD *)a1;
  v8 = a2;
  v6 = 1073741922;
  v7 = v2;
  v9 = 0;
  v3 = CApiPortClient::SendRequest(a1, &v6, 24, &v9, 0, 0);
  v4 = v3;
  if ( v3 < 0 )
    MilInstrumentationCheckHR_MaybeFailFast(4u, &qword_18001A010, 2, v3, 0x1Eu);
  else
    return (unsigned int)v9;
  return v4;
}

```

## disassembly

```asm
0x180011240  push    rbx
0x180011242  sub     rsp, 50h
0x180011246  movups  xmm0, xmmword ptr [rcx]
0x180011249  xor     eax, eax
0x18001124b  mov     [rsp+58h+var_14], edx
0x18001124f  mov     word ptr [rsp+58h+var_30], ax; void *
0x180011254  lea     r9, [rsp+58h+arg_8]; int *
0x180011259  lea     rdx, [rsp+58h+var_28]; void *
0x18001125e  mov     [rsp+58h+var_28], 40000062h
0x180011266  movdqu  [rsp+58h+var_24], xmm0
0x18001126c  lea     r8d, [rax+18h]; __int16
0x180011270  mov     [rsp+58h+arg_8], eax
0x180011274  mov     [rsp+58h+var_38], rax; void *
0x180011279  call    ?SendRequest@CApiPortClient@@QEAAJPEBXFPEAJPEAXF@Z; CApiPortClient::SendRequest(void const *,short,long *,void *,short)
0x18001127e  mov     ebx, eax
0x180011280  test    eax, eax
0x180011282  js      short loc_18001128A
0x180011284  mov     ebx, [rsp+58h+arg_8]
0x180011288  jmp     short loc_1800112AB
0x18001128a  mov     r8d, 2; unsigned int
0x180011290  mov     dword ptr [rsp+58h+var_38], 1Eh; unsigned int
0x180011298  mov     r9d, eax; int
0x18001129b  lea     rdx, qword_18001A010; int *
0x1800112a2  lea     ecx, [r8+2]; unsigned int
0x1800112a6  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x1800112ab  mov     eax, ebx
0x1800112ad  add     rsp, 50h
0x1800112b1  pop     rbx
0x1800112b2  retn
```
