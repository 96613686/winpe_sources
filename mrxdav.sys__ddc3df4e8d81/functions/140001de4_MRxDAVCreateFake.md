# MRxDAVCreateFake

- ea: `0x140001de4`
- end: `0x1400020eb`
- name: `MRxDAVCreateFake`
- size: `775`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1400130e0`

## callees

- `0x14000163c`
- `0x140001680`
- `0x1400017e4`
- `0x140001948`
- `0x140001de4`
- `0x140002824`
- `0x140025a08`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x140001e52`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140001f7f`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140001fce`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140002019`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400020b4`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140001e52`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140001f7f`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140001fce`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140002019`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400020b4`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x140001ed7`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x140001ed7`

## pseudocode

```c
__int64 __fastcall MRxDAVCreateFake(__int64 a1, __int64 a2)
{
  __int64 v3; // rcx
  const UNICODE_STRING *v5; // rsi
  __int64 v6; // r8
  _DWORD *v7; // r14
  __int64 v8; // rbx
  HANDLE CurrentThreadId; // rax
  const UNICODE_STRING *v10; // rbx
  __int64 v11; // rsi
  int v12; // ecx
  _DWORD *v13; // r8
  _DWORD *v14; // rdx
  __int64 v15; // rbx
  HANDLE v16; // rax
  unsigned int v17; // edi
  __int64 v18; // rbx
  HANDLE v19; // rax
  __int64 v20; // rbx
  HANDLE v21; // rax
  __int64 v22; // rbx
  HANDLE v23; // rax
  unsigned int v25; // [rsp+80h] [rbp+8h] BYREF

  v3 = *(_QWORD *)(a1 + 56);
  v25 = 0;
  v5 = 0;
  v6 = *(_QWORD *)(*(_QWORD *)(a1 + 72) + 40LL);
  if ( v6 )
    v5 = *(const UNICODE_STRING **)(v6 + 40);
  v7 = 0;
  if ( v3 )
    v7 = *(_DWORD **)(v3 + 136);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
  {
    v8 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    CurrentThreadId = PsGetCurrentThreadId();
    WPP_SF_qq(v8, 137, WPP_d37f3b85fd70300967c551fc1b4b0e40_Traceguids, CurrentThreadId, a1);
  }
  v10 = v5 + 7;
  if ( !v5[7].Length )
    goto LABEL_42;
  v11 = *(_QWORD *)(a1 + 56);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
    WPP_SF_ZZ(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      138,
      (unsigned int)WPP_d37f3b85fd70300967c551fc1b4b0e40_Traceguids,
      v11 + 360,
      (__int64)v10);
  if ( *(_WORD *)(v11 + 360) >= v10->Length || !RtlPrefixUnicodeString((PCUNICODE_STRING)(v11 + 360), v10, 1u) )
    goto LABEL_42;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 3), 139, WPP_d37f3b85fd70300967c551fc1b4b0e40_Traceguids);
  if ( (unsigned __int8)MRxDAVIsFileInfoCacheFound(a1, a2, &v25, v10) )
  {
    v12 = *(_DWORD *)(a2 + 32);
    v13 = (_DWORD *)(a1 + 536);
    if ( (v12 & 1) != 0 )
    {
      if ( (*v13 & 0xFFFFFFFA) == 0 && *v13 != 1
        || (v14 = (_DWORD *)(a1 + 540), _bittest((const signed __int32 *)(a1 + 540), 0xCu))
        || (*(_DWORD *)(a1 + 512) & 0x50000006) != 0 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
        {
          v15 = *((_QWORD *)WPP_GLOBAL_Control + 3);
          v16 = PsGetCurrentThreadId();
          WPP_SF_q(v15, 141, WPP_d37f3b85fd70300967c551fc1b4b0e40_Traceguids, v16);
        }
LABEL_26:
        v17 = -1073741790;
        goto LABEL_45;
      }
    }
    else
    {
      v14 = (_DWORD *)(a1 + 540);
    }
    if ( *v13 == 2 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
      {
        v18 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v19 = PsGetCurrentThreadId();
        WPP_SF_q(v18, 142, WPP_d37f3b85fd70300967c551fc1b4b0e40_Traceguids, v19);
      }
      v17 = -1073741771;
    }
    else
    {
      if ( (*v14 & 0x40) == 0 )
      {
        if ( (*(_DWORD *)(a1 + 512) & 0x10000) == 0 && (*v14 & 0x1000) == 0 )
        {
          v17 = v25;
          *(_DWORD *)(a2 + 32) = v12 | 0x10;
          *v7 = 1;
          goto LABEL_45;
        }
        goto LABEL_26;
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
      {
        v20 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v21 = PsGetCurrentThreadId();
        WPP_SF_q(v20, 143, WPP_d37f3b85fd70300967c551fc1b4b0e40_Traceguids, v21);
      }
      v17 = -1073741638;
    }
  }
  else
  {
LABEL_42:
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 3), 140, WPP_d37f3b85fd70300967c551fc1b4b0e40_Traceguids);
    v17 = -1073741823;
  }
LABEL_45:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
  {
    v22 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v23 = PsGetCurrentThreadId();
    WPP_SF_qD(v22, 144, WPP_d37f3b85fd70300967c551fc1b4b0e40_Traceguids, v23, v17);
  }
  return v17;
}

```

## disassembly

```asm
0x140001de4  mov     rax, rsp
0x140001de7  push    rbx
0x140001de8  push    rbp
0x140001de9  push    rsi
0x140001dea  push    rdi
0x140001deb  push    r12
0x140001ded  push    r13
0x140001def  push    r14
0x140001df1  push    r15
0x140001df3  sub     rsp, 38h
0x140001df7  xor     r15d, r15d
0x140001dfa  mov     rdi, rcx
0x140001dfd  mov     rcx, [rcx+38h]
0x140001e01  mov     rbp, rdx
0x140001e04  mov     [rax+8], r15d
0x140001e08  mov     esi, r15d
0x140001e0b  mov     rax, [rdi+48h]
0x140001e0f  mov     r8, [rax+28h]
0x140001e13  test    r8, r8
0x140001e16  jz      short loc_140001E1C
0x140001e18  mov     rsi, [r8+28h]
0x140001e1c  mov     r14, r15
0x140001e1f  test    rcx, rcx
0x140001e22  jz      short loc_140001E2B
0x140001e24  mov     r14, [rcx+88h]
0x140001e2b  mov     rbx, cs:WPP_GLOBAL_Control
0x140001e32  lea     r12, WPP_GLOBAL_Control
0x140001e39  lea     r13, WPP_d37f3b85fd70300967c551fc1b4b0e40_Traceguids
0x140001e40  cmp     rbx, r12
0x140001e43  jz      short loc_140001E76
0x140001e45  test    dword ptr [rbx+2Ch], 2000h
0x140001e4c  jz      short loc_140001E76
0x140001e4e  mov     rbx, [rbx+18h]
0x140001e52  call    cs:__imp_PsGetCurrentThreadId
0x140001e59  nop     dword ptr [rax+rax+00h]
0x140001e5e  mov     edx, 89h
0x140001e63  mov     [rsp+78h+var_58], rdi
0x140001e68  mov     r9, rax
0x140001e6b  mov     r8, r13
0x140001e6e  mov     rcx, rbx
0x140001e71  call    WPP_SF_qq
0x140001e76  lea     rbx, [rsi+70h]
0x140001e7a  cmp     [rbx], r15w
0x140001e7e  jz      loc_140002070
0x140001e84  mov     rsi, [rdi+38h]
0x140001e88  mov     rcx, cs:WPP_GLOBAL_Control
0x140001e8f  cmp     rcx, r12
0x140001e92  jz      short loc_140001EBA
0x140001e94  test    dword ptr [rcx+2Ch], 4000h
0x140001e9b  jz      short loc_140001EBA
0x140001e9d  mov     rcx, [rcx+18h]
0x140001ea1  lea     r9, [rsi+168h]
0x140001ea8  mov     edx, 8Ah
0x140001ead  mov     [rsp+78h+var_58], rbx
0x140001eb2  mov     r8, r13
0x140001eb5  call    WPP_SF_ZZ
0x140001eba  movzx   eax, word ptr [rbx]
0x140001ebd  cmp     [rsi+168h], ax
0x140001ec4  jnb     loc_140002070
0x140001eca  mov     r8b, 1; CaseInSensitive
0x140001ecd  lea     rcx, [rsi+168h]; String1
0x140001ed4  mov     rdx, rbx; String2
0x140001ed7  call    cs:__imp_RtlPrefixUnicodeString
0x140001ede  nop     dword ptr [rax+rax+00h]
0x140001ee3  test    al, al
0x140001ee5  jz      loc_140002070
0x140001eeb  mov     rcx, cs:WPP_GLOBAL_Control
0x140001ef2  cmp     rcx, r12
0x140001ef5  jz      short loc_140001F11
0x140001ef7  test    dword ptr [rcx+2Ch], 4000h
0x140001efe  jz      short loc_140001F11
0x140001f00  mov     rcx, [rcx+18h]
0x140001f04  mov     edx, 8Bh
0x140001f09  mov     r8, r13
0x140001f0c  call    WPP_SF_
0x140001f11  mov     r9, rbx
0x140001f14  lea     r8, [rsp+78h+arg_0]
0x140001f1c  mov     rdx, rbp
0x140001f1f  mov     rcx, rdi
0x140001f22  call    MRxDAVIsFileInfoCacheFound
0x140001f27  test    al, al
0x140001f29  jz      loc_140002070
0x140001f2f  mov     ecx, [rbp+20h]
0x140001f32  lea     r8, [rdi+218h]
0x140001f39  test    cl, 1
0x140001f3c  jz      short loc_140001FA8
0x140001f3e  mov     eax, [r8]
0x140001f41  test    eax, 0FFFFFFFAh
0x140001f46  jnz     short loc_140001F4D
0x140001f48  cmp     eax, 1
0x140001f4b  jnz     short loc_140001F66
0x140001f4d  lea     rdx, [rdi+21Ch]
0x140001f54  bt      dword ptr [rdx], 0Ch
0x140001f58  jb      short loc_140001F66
0x140001f5a  test    dword ptr [rdi+200h], 50000006h
0x140001f64  jz      short loc_140001FAF
0x140001f66  mov     rbx, cs:WPP_GLOBAL_Control
0x140001f6d  cmp     rbx, r12
0x140001f70  jz      short loc_140001F9E
0x140001f72  test    dword ptr [rbx+2Ch], 2000h
0x140001f79  jz      short loc_140001F9E
0x140001f7b  mov     rbx, [rbx+18h]
0x140001f7f  call    cs:__imp_PsGetCurrentThreadId
0x140001f86  nop     dword ptr [rax+rax+00h]
0x140001f8b  mov     edx, 8Dh
0x140001f90  mov     r8, r13
0x140001f93  mov     r9, rax
0x140001f96  mov     rcx, rbx
0x140001f99  call    WPP_SF_q
0x140001f9e  mov     edi, 0C0000022h
0x140001fa3  jmp     loc_14000209B
0x140001fa8  lea     rdx, [rdi+21Ch]
0x140001faf  cmp     dword ptr [r8], 2
0x140001fb3  jnz     short loc_140001FF7
0x140001fb5  mov     rbx, cs:WPP_GLOBAL_Control
0x140001fbc  cmp     rbx, r12
0x140001fbf  jz      short loc_140001FED
0x140001fc1  test    dword ptr [rbx+2Ch], 2000h
0x140001fc8  jz      short loc_140001FED
0x140001fca  mov     rbx, [rbx+18h]
0x140001fce  call    cs:__imp_PsGetCurrentThreadId
0x140001fd5  nop     dword ptr [rax+rax+00h]
0x140001fda  mov     edx, 8Eh
0x140001fdf  mov     r8, r13
0x140001fe2  mov     r9, rax
0x140001fe5  mov     rcx, rbx
0x140001fe8  call    WPP_SF_q
0x140001fed  mov     edi, 0C0000035h
0x140001ff2  jmp     loc_14000209B
0x140001ff7  mov     r8d, [rdx]
0x140001ffa  test    r8b, 40h
0x140001ffe  jz      short loc_14000203F
0x140002000  mov     rbx, cs:WPP_GLOBAL_Control
0x140002007  cmp     rbx, r12
0x14000200a  jz      short loc_140002038
0x14000200c  test    dword ptr [rbx+2Ch], 2000h
0x140002013  jz      short loc_140002038
0x140002015  mov     rbx, [rbx+18h]
0x140002019  call    cs:__imp_PsGetCurrentThreadId
0x140002020  nop     dword ptr [rax+rax+00h]
0x140002025  mov     edx, 8Fh
0x14000202a  mov     r8, r13
0x14000202d  mov     r9, rax
0x140002030  mov     rcx, rbx
0x140002033  call    WPP_SF_q
0x140002038  mov     edi, 0C00000BAh
0x14000203d  jmp     short loc_14000209B
0x14000203f  test    dword ptr [rdi+200h], 10000h
0x140002049  jnz     loc_140001F9E
0x14000204f  bt      r8d, 0Ch
0x140002054  jb      loc_140001F9E
0x14000205a  mov     edi, [rsp+78h+arg_0]
0x140002061  or      ecx, 10h
0x140002064  mov     [rbp+20h], ecx
0x140002067  mov     dword ptr [r14], 1
0x14000206e  jmp     short loc_14000209B
0x140002070  mov     rcx, cs:WPP_GLOBAL_Control
0x140002077  cmp     rcx, r12
0x14000207a  jz      short loc_140002096
0x14000207c  test    dword ptr [rcx+2Ch], 4000h
0x140002083  jz      short loc_140002096
0x140002085  mov     rcx, [rcx+18h]
0x140002089  mov     edx, 8Ch
0x14000208e  mov     r8, r13
0x140002091  call    WPP_SF_
0x140002096  mov     edi, 0C0000001h
0x14000209b  mov     rbx, cs:WPP_GLOBAL_Control
0x1400020a2  cmp     rbx, r12
0x1400020a5  jz      short loc_1400020D7
0x1400020a7  test    dword ptr [rbx+2Ch], 2000h
0x1400020ae  jz      short loc_1400020D7
0x1400020b0  mov     rbx, [rbx+18h]
0x1400020b4  call    cs:__imp_PsGetCurrentThreadId
0x1400020bb  nop     dword ptr [rax+rax+00h]
0x1400020c0  mov     edx, 90h
0x1400020c5  mov     dword ptr [rsp+78h+var_58], edi
0x1400020c9  mov     r9, rax
0x1400020cc  mov     r8, r13
0x1400020cf  mov     rcx, rbx
0x1400020d2  call    WPP_SF_qD
0x1400020d7  mov     eax, edi
0x1400020d9  add     rsp, 38h
0x1400020dd  pop     r15
0x1400020df  pop     r14
0x1400020e1  pop     r13
0x1400020e3  pop     r12
0x1400020e5  pop     rdi
0x1400020e6  pop     rsi
0x1400020e7  pop     rbp
0x1400020e8  pop     rbx
0x1400020e9  retn
```
