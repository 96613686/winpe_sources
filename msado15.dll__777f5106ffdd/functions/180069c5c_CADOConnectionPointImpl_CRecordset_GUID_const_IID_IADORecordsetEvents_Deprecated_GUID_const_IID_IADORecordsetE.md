# CADOConnectionPointImpl<CRecordset,&_GUID const IID_IADORecordsetEvents_Deprecated,&_GUID const IID_IADORecordsetEventsVt_Deprecated>::FireEvent(CNfyConnection *,CNfyContext &)

- ea: `0x180069c5c`
- end: `0x180069f1f`
- name: `?FireEvent@?$CADOConnectionPointImpl@VCRecordset@@$1?IID_IADORecordsetEvents_Deprecated@@3U_GUID@@B$1?IID_IADORecordsetEventsVt_Deprecated@@3U3@B@@QEAAJPEAVCNfyConnection@@AEAVCNfyContext@@@Z`
- size: `707`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180069aec`
- `0x1800a5550`

## callees

- `0x180065054`
- `0x180069c5c`
- `0x1800c9788`
- `0x1800d0010`

## import_xrefs

- `MSDART!MpHeapAlloc` at `0x180069cbd`
- `MSDART!MpHeapAlloc` at `0x180069d6f`
- `MSDART!MpHeapAlloc` at `0x180069cbd`
- `MSDART!MpHeapAlloc` at `0x180069d6f`
- `MSDART!MpHeapFree` at `0x180069e6b`
- `MSDART!MpHeapFree` at `0x180069e6b`
- `KERNEL32!GetCurrentThreadId` at `0x180069c75`
- `KERNEL32!GetCurrentThreadId` at `0x180069c75`
- `KERNEL32!TlsSetValue` at `0x180069e55`
- `KERNEL32!TlsSetValue` at `0x180069e55`
- `KERNEL32!TlsGetValue` at `0x180069d36`
- `KERNEL32!TlsGetValue` at `0x180069d36`
- `USER32!PostMessageW` at `0x180069d19`
- `USER32!PostMessageW` at `0x180069d19`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CADOConnectionPointImpl<CRecordset,&_GUID const IID_IADORecordsetEvents_Deprecated,&_GUID const IID_IADORecordsetEventsVt_Deprecated>::FireEvent(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  DWORD CurrentThreadId; // eax
  int v7; // r13d
  CAsyncNfyContext *v8; // rax
  CAsyncNfyContext *v9; // r9
  _OWORD *Value; // rsi
  _OWORD *v12; // rax
  _OWORD *v13; // r15
  unsigned int v14; // r14d
  unsigned int v15; // eax
  char v16; // [rsp+98h] [rbp+10h]
  _OWORD *v17; // [rsp+A8h] [rbp+20h]

  CurrentThreadId = GetCurrentThreadId();
  v7 = **(_DWORD **)(a3 + 224);
  if ( CurrentThreadId != *(_DWORD *)(a2 + 4) && CurrentThreadId != *(_DWORD *)(a1 + 24) )
  {
    if ( *(_BYTE *)a2 )
    {
      v8 = (CAsyncNfyContext *)MpHeapAlloc(g_hHeapHandle, 10485760, 272);
      if ( v8 )
        v9 = CAsyncNfyContext::CAsyncNfyContext(v8, (const struct CNfyContext *)a3);
      else
        v9 = 0;
      if ( v9 )
      {
        if ( *((_BYTE *)qword_1800E8730 + *(int *)(a3 + 192)) )
          *((_DWORD *)v9 + 66) = 3;
        PostMessageW(*(HWND *)(a1 + 32), 0x2001u, 0, (LPARAM)v9);
      }
      return 0;
    }
LABEL_22:
    v15 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)a1 + 88LL))(a1, a2, a3);
    goto LABEL_23;
  }
  Value = TlsGetValue(*((_DWORD *)g_pStaticGlobals + 5));
  if ( Value )
  {
    v16 = 0;
    v12 = (_OWORD *)MpHeapAlloc(g_hHeapHandle, 10485760, 48);
    v13 = v12;
    v17 = v12;
    if ( v12 )
    {
      *v12 = *Value;
      v12[1] = Value[1];
      v12[2] = Value[2];
      v16 = 1;
      *Value = 0;
      Value[1] = 0;
      Value[2] = 0;
      *((_BYTE *)Value + 30) = 1;
    }
    try
    {
      if ( *(_BYTE *)a2 )
        v14 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, GUID *, __int64, __int16, __int64, _QWORD, _QWORD, _QWORD))(**(_QWORD **)(a2 + 8) + 48LL))(
                *(_QWORD *)(a2 + 8),
                *(unsigned int *)(a3 + 192),
                &GUID_NULL,
                2048,
                1,
                a3 + 200,
                0,
                0,
                0);
      else
        v14 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)a1 + 88LL))(a1, a2, a3);
    }
    catch ( ... )
    {
      if ( v17 )
      {
        if ( v16 )
        {
          *Value = *v17;
          Value[1] = v17[1];
          Value[2] = v17[2];
        }
        TlsSetValue(*((_DWORD *)g_pStaticGlobals + 5), Value);
        MpHeapFree(g_hHeapHandle, v17);
      }
      throw;
    }
    if ( v13 )
    {
      *Value = *v13;
      Value[1] = v13[1];
      Value[2] = v13[2];
      TlsSetValue(*((_DWORD *)g_pStaticGlobals + 5), Value);
      MpHeapFree(g_hHeapHandle, v13);
    }
    goto LABEL_24;
  }
  if ( !*(_BYTE *)a2 )
    goto LABEL_22;
  v15 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, GUID *, __int64, __int16, __int64, _QWORD, _QWORD, _QWORD))(**(_QWORD **)(a2 + 8) + 48LL))(
          *(_QWORD *)(a2 + 8),
          *(unsigned int *)(a3 + 192),
          &GUID_NULL,
          2048,
          1,
          a3 + 200,
          0,
          0,
          0);
LABEL_23:
  v14 = v15;
LABEL_24:
  if ( *((_BYTE *)qword_1800E8730 + *(int *)(a3 + 192)) && v7 != 3 && **(_DWORD **)(a3 + 224) == 4 )
    CNfyContext::GenerateCancelError((CNfyContext *)a3);
  return v14;
}

```

## disassembly

```asm
0x180069c5c  push    rbx
0x180069c5e  push    rsi
0x180069c5f  push    rdi
0x180069c60  push    r12
0x180069c62  push    r13
0x180069c64  push    r14
0x180069c66  push    r15
0x180069c68  sub     rsp, 50h
0x180069c6c  mov     rdi, r8
0x180069c6f  mov     r14, rdx
0x180069c72  mov     r12, rcx
0x180069c75  call    cs:__imp_GetCurrentThreadId
0x180069c7c  nop     dword ptr [rax+rax+00h]
0x180069c81  mov     r9, [rdi+0E0h]
0x180069c88  mov     r13d, [r9]
0x180069c8b  cmp     eax, [r14+4]
0x180069c8f  jz      loc_180069D2C
0x180069c95  cmp     eax, [r12+18h]
0x180069c9a  jz      loc_180069D2C
0x180069ca0  xor     ebx, ebx
0x180069ca2  cmp     [r14], bl
0x180069ca5  jz      loc_180069EC5
0x180069cab  mov     edx, 0A00000h
0x180069cb0  mov     r8d, 110h
0x180069cb6  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x180069cbd  call    cs:__imp_MpHeapAlloc
0x180069cc4  nop     dword ptr [rax+rax+00h]
0x180069cc9  mov     [rsp+88h+arg_8], rax
0x180069cd1  test    rax, rax
0x180069cd4  jz      short loc_180069CE6
0x180069cd6  mov     rdx, rdi; struct CNfyContext *
0x180069cd9  mov     rcx, rax; this
0x180069cdc  call    ??0CAsyncNfyContext@@QEAA@AEBVCNfyContext@@@Z; CAsyncNfyContext::CAsyncNfyContext(CNfyContext const &)
0x180069ce1  mov     r9, rax
0x180069ce4  jmp     short loc_180069CE9
0x180069ce6  mov     r9, rbx; lParam
0x180069ce9  test    r9, r9
0x180069cec  jz      short loc_180069D25
0x180069cee  movsxd  rax, dword ptr [rdi+0C0h]
0x180069cf5  lea     rcx, qword_1800E8730
0x180069cfc  cmp     [rax+rcx], bl
0x180069cff  jz      short loc_180069D0C
0x180069d01  mov     dword ptr [r9+108h], 3
0x180069d0c  xor     r8d, r8d; wParam
0x180069d0f  mov     edx, 2001h; Msg
0x180069d14  mov     rcx, [r12+20h]; hWnd
0x180069d19  call    cs:__imp_PostMessageW
0x180069d20  nop     dword ptr [rax+rax+00h]
0x180069d25  xor     eax, eax
0x180069d27  jmp     loc_180069F0E
0x180069d2c  mov     rcx, cs:?g_pStaticGlobals@@3PEAVCDAOStaticGlobals@@EA; CDAOStaticGlobals * g_pStaticGlobals
0x180069d33  mov     ecx, [rcx+14h]; dwTlsIndex
0x180069d36  call    cs:__imp_TlsGetValue
0x180069d3d  nop     dword ptr [rax+rax+00h]
0x180069d42  mov     rsi, rax
0x180069d45  mov     [rsp+88h+arg_10], rax
0x180069d4d  xor     ebx, ebx
0x180069d4f  test    rax, rax
0x180069d52  jz      loc_180069E79
0x180069d58  mov     byte ptr [rsp+88h+arg_8], bl
0x180069d5f  mov     edx, 0A00000h
0x180069d64  lea     r8d, [rbx+30h]
0x180069d68  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x180069d6f  call    cs:__imp_MpHeapAlloc
0x180069d76  nop     dword ptr [rax+rax+00h]
0x180069d7b  mov     r15, rax
0x180069d7e  mov     [rsp+88h+arg_18], rax
0x180069d86  lea     r8d, [rbx+1]
0x180069d8a  test    rax, rax
0x180069d8d  jz      short loc_180069DBF
0x180069d8f  movups  xmm0, xmmword ptr [rsi]
0x180069d92  movups  xmmword ptr [rax], xmm0
0x180069d95  movups  xmm1, xmmword ptr [rsi+10h]
0x180069d99  movups  xmmword ptr [rax+10h], xmm1
0x180069d9d  movups  xmm0, xmmword ptr [rsi+20h]
0x180069da1  movups  xmmword ptr [rax+20h], xmm0
0x180069da5  mov     byte ptr [rsp+88h+arg_8], r8b
0x180069dad  xorps   xmm0, xmm0
0x180069db0  movups  xmmword ptr [rsi], xmm0
0x180069db3  movups  xmmword ptr [rsi+10h], xmm0
0x180069db7  movups  xmmword ptr [rsi+20h], xmm0
0x180069dbb  mov     [rsi+1Eh], r8b
0x180069dbf  cmp     [r14], bl
0x180069dc2  jz      short loc_180069E0D
0x180069dc4  mov     rcx, [r14+8]
0x180069dc8  mov     rax, [rcx]
0x180069dcb  lea     rdx, [rdi+0C8h]
0x180069dd2  mov     [rsp+88h+var_48], rbx
0x180069dd7  mov     [rsp+88h+var_50], rbx
0x180069ddc  mov     [rsp+88h+var_58], rbx
0x180069de1  mov     [rsp+88h+var_60], rdx
0x180069de6  mov     [rsp+88h+var_68], r8w
0x180069dec  mov     r9d, 800h
0x180069df2  lea     r8, GUID_NULL
0x180069df9  mov     edx, [rdi+0C0h]
0x180069dff  mov     rax, [rax+30h]
0x180069e03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069e08  mov     r14d, eax
0x180069e0b  jmp     short loc_180069E26
0x180069e0d  mov     rax, [r12]
0x180069e11  mov     r8, rdi
0x180069e14  mov     rdx, r14
0x180069e17  mov     rcx, r12
0x180069e1a  mov     rax, [rax+58h]
0x180069e1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069e23  mov     r14d, eax
0x180069e26  test    r15, r15
0x180069e29  jz      loc_180069EDE
0x180069e2f  movups  xmm0, xmmword ptr [r15]
0x180069e33  movups  xmmword ptr [rsi], xmm0
0x180069e36  movups  xmm1, xmmword ptr [r15+10h]
0x180069e3b  movups  xmmword ptr [rsi+10h], xmm1
0x180069e3f  movups  xmm0, xmmword ptr [r15+20h]
0x180069e44  movups  xmmword ptr [rsi+20h], xmm0
0x180069e48  mov     rdx, rsi; lpTlsValue
0x180069e4b  mov     rcx, cs:?g_pStaticGlobals@@3PEAVCDAOStaticGlobals@@EA; CDAOStaticGlobals * g_pStaticGlobals
0x180069e52  mov     ecx, [rcx+14h]; dwTlsIndex
0x180069e55  call    cs:__imp_TlsSetValue
0x180069e5c  nop     dword ptr [rax+rax+00h]
0x180069e61  mov     rdx, r15
0x180069e64  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x180069e6b  call    cs:__imp_MpHeapFree
0x180069e72  nop     dword ptr [rax+rax+00h]
0x180069e77  jmp     short loc_180069EDE
0x180069e79  cmp     [r14], bl
0x180069e7c  jz      short loc_180069EC5
0x180069e7e  mov     rcx, [r14+8]
0x180069e82  mov     rax, [rcx]
0x180069e85  lea     rdx, [rdi+0C8h]
0x180069e8c  mov     [rsp+88h+var_48], rbx
0x180069e91  mov     [rsp+88h+var_50], rbx
0x180069e96  mov     [rsp+88h+var_58], rbx
0x180069e9b  mov     [rsp+88h+var_60], rdx
0x180069ea0  mov     [rsp+88h+var_68], 1
0x180069ea7  mov     r9d, 800h
0x180069ead  lea     r8, GUID_NULL
0x180069eb4  mov     edx, [rdi+0C0h]
0x180069eba  mov     rax, [rax+30h]
0x180069ebe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069ec3  jmp     short loc_180069EDB
0x180069ec5  mov     rax, [r12]
0x180069ec9  mov     r8, rdi
0x180069ecc  mov     rdx, r14
0x180069ecf  mov     rcx, r12
0x180069ed2  mov     rax, [rax+58h]
0x180069ed6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069edb  mov     r14d, eax
0x180069ede  movsxd  rax, dword ptr [rdi+0C0h]
0x180069ee5  lea     rcx, qword_1800E8730
0x180069eec  cmp     [rax+rcx], bl
0x180069eef  jz      short loc_180069F0B
0x180069ef1  cmp     r13d, 3
0x180069ef5  jz      short loc_180069F0B
0x180069ef7  mov     rax, [rdi+0E0h]
0x180069efe  cmp     dword ptr [rax], 4
0x180069f01  jnz     short loc_180069F0B
0x180069f03  mov     rcx, rdi; this
0x180069f06  call    ?GenerateCancelError@CNfyContext@@QEAAXXZ; CNfyContext::GenerateCancelError(void)
0x180069f0b  mov     eax, r14d
0x180069f0e  add     rsp, 50h
0x180069f12  pop     r15
0x180069f14  pop     r14
0x180069f16  pop     r13
0x180069f18  pop     r12
0x180069f1a  pop     rdi
0x180069f1b  pop     rsi
0x180069f1c  pop     rbx
0x180069f1d  retn
```
