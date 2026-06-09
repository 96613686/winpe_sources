# MRxDAVFormatUserModeFcbFinalizeRequest

- ea: `0x140003c20`
- end: `0x140003dbd`
- name: `MRxDAVFormatUserModeFcbFinalizeRequest`
- size: `413`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x14000163c`
- `0x140001680`
- `0x140001b64`
- `0x140003c20`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x140003c54`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140003c90`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140003d88`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140003c54`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140003c90`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140003d88`

## pseudocode

```c
__int64 __fastcall MRxDAVFormatUserModeFcbFinalizeRequest(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v6; // rbx
  HANDLE CurrentThreadId; // rax
  __int64 v8; // rbx
  HANDLE v9; // rax
  __int64 v10; // rax
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // rcx
  _WORD *v14; // r10
  __int64 v15; // r9
  _WORD *v16; // rax
  _WORD *v17; // rcx
  _WORD *v18; // rax
  _WORD *v19; // rcx
  __int64 v20; // rdx
  _WORD *v21; // rcx
  __int64 v22; // rbx
  HANDLE v23; // rax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
    {
      v6 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      CurrentThreadId = PsGetCurrentThreadId();
      WPP_SF_q(v6, 28, WPP_5c72cb21a1353022f2b3482a62d37e3d_Traceguids, CurrentThreadId);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
    {
      v8 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v9 = PsGetCurrentThreadId();
      WPP_SF_qqq(v8, 29, WPP_5c72cb21a1353022f2b3482a62d37e3d_Traceguids, v9, a1, a2);
    }
  }
  v10 = *(_QWORD *)(a2 + 216);
  v11 = 0;
  if ( v10 )
    v11 = *(_QWORD *)(v10 + 136);
  v12 = 2147483646;
  *(_DWORD *)(a3 + 48) = 7;
  v13 = 2147483646;
  v14 = (_WORD *)(v11 + 668);
  v15 = 260;
  v16 = (_WORD *)(a3 + 632);
  do
  {
    if ( !v13 )
      break;
    if ( !*v14 )
      break;
    *v16++ = *v14++;
    --v13;
    --v15;
  }
  while ( v15 );
  v17 = v16 - 1;
  if ( v15 )
    v17 = v16;
  v18 = (_WORD *)(a3 + 1152);
  *v17 = 0;
  v19 = (_WORD *)(v11 + 1188);
  v20 = 520;
  do
  {
    if ( !v12 )
      break;
    if ( !*v19 )
      break;
    *v18++ = *v19++;
    --v12;
    --v20;
  }
  while ( v20 );
  v21 = v18 - 1;
  if ( v20 )
    v21 = v18;
  *v21 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
  {
    v22 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v23 = PsGetCurrentThreadId();
    WPP_SF_qD(v22, 30, WPP_5c72cb21a1353022f2b3482a62d37e3d_Traceguids, v23, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x140003c20  push    rbx
0x140003c22  push    rbp
0x140003c23  push    rsi
0x140003c24  push    rdi
0x140003c25  push    r14
0x140003c27  sub     rsp, 30h
0x140003c2b  mov     rsi, r8
0x140003c2e  mov     rdi, rdx
0x140003c31  mov     rbp, rcx
0x140003c34  mov     rbx, cs:WPP_GLOBAL_Control
0x140003c3b  lea     r14, WPP_GLOBAL_Control
0x140003c42  cmp     rbx, r14
0x140003c45  jz      short loc_140003CBD
0x140003c47  test    dword ptr [rbx+2Ch], 4000h
0x140003c4e  jz      short loc_140003C77
0x140003c50  mov     rbx, [rbx+18h]
0x140003c54  call    cs:__imp_PsGetCurrentThreadId
0x140003c5b  nop     dword ptr [rax+rax+00h]
0x140003c60  mov     edx, 1Ch
0x140003c65  lea     r8, WPP_5c72cb21a1353022f2b3482a62d37e3d_Traceguids
0x140003c6c  mov     r9, rax
0x140003c6f  mov     rcx, rbx
0x140003c72  call    WPP_SF_q
0x140003c77  mov     rbx, cs:WPP_GLOBAL_Control
0x140003c7e  cmp     rbx, r14
0x140003c81  jz      short loc_140003CBD
0x140003c83  test    dword ptr [rbx+2Ch], 2000h
0x140003c8a  jz      short loc_140003CBD
0x140003c8c  mov     rbx, [rbx+18h]
0x140003c90  call    cs:__imp_PsGetCurrentThreadId
0x140003c97  nop     dword ptr [rax+rax+00h]
0x140003c9c  mov     edx, 1Dh
0x140003ca1  mov     [rsp+58h+var_30], rdi
0x140003ca6  mov     r9, rax
0x140003ca9  mov     [rsp+58h+var_38], rbp
0x140003cae  lea     r8, WPP_5c72cb21a1353022f2b3482a62d37e3d_Traceguids
0x140003cb5  mov     rcx, rbx
0x140003cb8  call    WPP_SF_qqq
0x140003cbd  mov     rax, [rdi+0D8h]
0x140003cc4  xor     edi, edi
0x140003cc6  mov     edx, edi
0x140003cc8  test    rax, rax
0x140003ccb  jz      short loc_140003CD4
0x140003ccd  mov     rdx, [rax+88h]
0x140003cd4  mov     r8d, 7FFFFFFEh
0x140003cda  mov     dword ptr [rsi+30h], 7
0x140003ce1  mov     ecx, r8d
0x140003ce4  lea     r10, [rdx+29Ch]
0x140003ceb  mov     r9d, 104h
0x140003cf1  lea     rax, [rsi+278h]
0x140003cf8  test    rcx, rcx
0x140003cfb  jz      short loc_140003D1C
0x140003cfd  movzx   r11d, word ptr [r10]
0x140003d01  test    r11w, r11w
0x140003d05  jz      short loc_140003D1C
0x140003d07  mov     [rax], r11w
0x140003d0b  add     r10, 2
0x140003d0f  add     rax, 2
0x140003d13  dec     rcx
0x140003d16  sub     r9, 1
0x140003d1a  jnz     short loc_140003CF8
0x140003d1c  lea     rcx, [rax-2]
0x140003d20  test    r9, r9
0x140003d23  cmovnz  rcx, rax
0x140003d27  lea     rax, [rsi+480h]
0x140003d2e  mov     [rcx], di
0x140003d31  lea     rcx, [rdx+4A4h]
0x140003d38  mov     edx, 208h
0x140003d3d  test    r8, r8
0x140003d40  jz      short loc_140003D61
0x140003d42  movzx   r9d, word ptr [rcx]
0x140003d46  test    r9w, r9w
0x140003d4a  jz      short loc_140003D61
0x140003d4c  mov     [rax], r9w
0x140003d50  add     rcx, 2
0x140003d54  add     rax, 2
0x140003d58  dec     r8
0x140003d5b  sub     rdx, 1
0x140003d5f  jnz     short loc_140003D3D
0x140003d61  test    rdx, rdx
0x140003d64  lea     rcx, [rax-2]
0x140003d68  cmovnz  rcx, rax
0x140003d6c  mov     [rcx], di
0x140003d6f  mov     rbx, cs:WPP_GLOBAL_Control
0x140003d76  cmp     rbx, r14
0x140003d79  jz      short loc_140003DAF
0x140003d7b  test    dword ptr [rbx+2Ch], 4000h
0x140003d82  jz      short loc_140003DAF
0x140003d84  mov     rbx, [rbx+18h]
0x140003d88  call    cs:__imp_PsGetCurrentThreadId
0x140003d8f  nop     dword ptr [rax+rax+00h]
0x140003d94  mov     edx, 1Eh
0x140003d99  mov     dword ptr [rsp+58h+var_38], edi
0x140003d9d  mov     r9, rax
0x140003da0  lea     r8, WPP_5c72cb21a1353022f2b3482a62d37e3d_Traceguids
0x140003da7  mov     rcx, rbx
0x140003daa  call    WPP_SF_qD
0x140003daf  xor     eax, eax
0x140003db1  add     rsp, 30h
0x140003db5  pop     r14
0x140003db7  pop     rdi
0x140003db8  pop     rsi
0x140003db9  pop     rbp
0x140003dba  pop     rbx
0x140003dbb  retn
```
