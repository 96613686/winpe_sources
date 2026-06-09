# NatMergePortMapGuidListFromHNetConn(IHNetConnection *,_LIST_ENTRY *)

- ea: `0x18007a428`
- end: `0x18007a78f`
- name: `?NatMergePortMapGuidListFromHNetConn@@YAJPEAUIHNetConnection@@PEAU_LIST_ENTRY@@@Z`
- size: `871`
- prototype: `__int64 __fastcall(struct IHNetConnection *, struct _LIST_ENTRY *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18007c9ac`

## callees

- `0x18000c110`
- `0x18000c750`
- `0x18007a428`
- `0x180090010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007a61f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007a61f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007a631`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007a631`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18007a73d`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18007a73d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007a5de`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007a5de`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18007a48d`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18007a48d`

## pseudocode

```c
__int64 __fastcall NatMergePortMapGuidListFromHNetConn(struct IHNetConnection *a1, struct _LIST_ENTRY *a2)
{
  unsigned int v4; // eax
  __int64 v5; // rdx
  unsigned int v6; // ebx
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // rax
  int v10; // eax
  __m128i v11; // xmm6
  struct _LIST_ENTRY *Flink; // rcx
  unsigned __int64 v13; // xmm0_8
  unsigned __int64 v14; // rax
  HANDLE ProcessHeap; // rax
  __m128i *v16; // rax
  struct _LIST_ENTRY *Blink; // rcx
  _QWORD *v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // r9
  __int64 v22; // [rsp+30h] [rbp-30h] BYREF
  __int64 v23; // [rsp+38h] [rbp-28h] BYREF
  LPVOID pv[2]; // [rsp+40h] [rbp-20h] BYREF
  int v25; // [rsp+A0h] [rbp+40h] BYREF
  __int64 v26; // [rsp+A8h] [rbp+48h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 97, &WPP_dcce5e63c4ad32fefb8b293fcfca3143_Traceguids);
  }
  v4 = CoInitializeEx(0, 0);
  v6 = v4;
  if ( v4 == -2147417850 || !v4 )
  {
    v9 = *(_QWORD *)a1;
    LOBYTE(v5) = 1;
    v26 = 0;
    v4 = (*(__int64 (__fastcall **)(struct IHNetConnection *, __int64, __int64 *))(v9 + 104))(a1, v5, &v26);
    v6 = v4;
    if ( v4 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v8 = 99;
        goto LABEL_11;
      }
    }
    else
    {
LABEL_17:
      while ( 1 )
      {
        v25 = 0;
        v22 = 0;
        v10 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *, int *))(*(_QWORD *)v26 + 24LL))(
                v26,
                1,
                &v22,
                &v25);
        v6 = v10;
        if ( v10 < 0 )
          break;
        if ( !v25 )
        {
          v6 = 0;
          goto LABEL_50;
        }
        v23 = 0;
        v6 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v22 + 32LL))(v22, &v23);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
        if ( v6 )
        {
          v18 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v19 = 101;
LABEL_39:
            v20 = v6;
LABEL_49:
            WPP_SF_d(v18[2], v19, &WPP_dcce5e63c4ad32fefb8b293fcfca3143_Traceguids, v20);
            goto LABEL_50;
          }
          goto LABEL_50;
        }
        pv[0] = 0;
        v6 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v23 + 88LL))(v23, pv);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
        if ( v6 )
        {
          v18 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v19 = 102;
            goto LABEL_39;
          }
          goto LABEL_50;
        }
        v11 = *(__m128i *)pv[0];
        CoTaskMemFree(pv[0]);
        Flink = a2->Flink;
        v13 = _mm_srli_si128(v11, 8).m128i_u64[0];
        pv[0] = 0;
        while ( Flink != a2 )
        {
          v14 = v11.m128i_i64[0] - (unsigned __int64)Flink[1].Flink;
          if ( (struct _LIST_ENTRY *)v11.m128i_i64[0] == Flink[1].Flink )
            v14 = v13 - (unsigned __int64)Flink[1].Blink;
          if ( !v14 )
            goto LABEL_17;
          Flink = Flink->Flink;
        }
        ProcessHeap = GetProcessHeap();
        v16 = (__m128i *)HeapAlloc(ProcessHeap, 8u, 0x20u);
        if ( !v16 )
        {
          v6 = -2147024882;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 103, &WPP_dcce5e63c4ad32fefb8b293fcfca3143_Traceguids);
          }
          goto LABEL_50;
        }
        v16->m128i_i64[0] = 0;
        v16->m128i_i64[1] = 0;
        v16[1] = v11;
        Blink = a2->Blink;
        if ( Blink->Flink != a2 )
          __fastfail(3u);
        v16->m128i_i64[0] = (__int64)a2;
        v16->m128i_i64[1] = (__int64)Blink;
        Blink->Flink = (struct _LIST_ENTRY *)v16;
        a2->Blink = (struct _LIST_ENTRY *)v16;
      }
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v19 = 100;
        v20 = (unsigned int)v10;
        goto LABEL_49;
      }
LABEL_50:
      if ( v26 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
        v26 = 0;
      }
    }
  }
  else
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v8 = 98;
LABEL_11:
      WPP_SF_d(v7[2], v8, &WPP_dcce5e63c4ad32fefb8b293fcfca3143_Traceguids, v4);
    }
  }
  CoUninitialize();
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 104, &WPP_dcce5e63c4ad32fefb8b293fcfca3143_Traceguids, v6);
  }
  return v6;
}

```

## disassembly

```asm
0x18007a428  mov     [rsp-28h+arg_0], rbx
0x18007a42d  mov     [rsp-28h+arg_8], rsi
0x18007a432  push    rbp
0x18007a433  push    rdi
0x18007a434  push    r12
0x18007a436  push    r13
0x18007a438  push    r15
0x18007a43a  mov     rbp, rsp
0x18007a43d  sub     rsp, 60h
0x18007a441  movaps  [rsp+60h+var_10], xmm6
0x18007a446  mov     rdi, rdx
0x18007a449  mov     rsi, rcx
0x18007a44c  mov     rcx, cs:WPP_GLOBAL_Control
0x18007a453  lea     r12, WPP_GLOBAL_Control
0x18007a45a  lea     r13, WPP_dcce5e63c4ad32fefb8b293fcfca3143_Traceguids
0x18007a461  mov     r15d, 200h
0x18007a467  cmp     rcx, r12
0x18007a46a  jz      short loc_18007A489
0x18007a46c  test    [rcx+1Ch], r15d
0x18007a470  jz      short loc_18007A489
0x18007a472  cmp     byte ptr [rcx+19h], 6
0x18007a476  jb      short loc_18007A489
0x18007a478  mov     rcx, [rcx+10h]
0x18007a47c  mov     edx, 61h ; 'a'
0x18007a481  mov     r8, r13
0x18007a484  call    WPP_SF_
0x18007a489  xor     edx, edx; dwCoInit
0x18007a48b  xor     ecx, ecx; pvReserved
0x18007a48d  call    cs:__imp_CoInitializeEx
0x18007a493  mov     ebx, eax
0x18007a495  cmp     eax, 80010106h
0x18007a49a  jz      short loc_18007A4DD
0x18007a49c  test    eax, eax
0x18007a49e  jz      short loc_18007A4DD
0x18007a4a0  mov     rcx, cs:WPP_GLOBAL_Control
0x18007a4a7  cmp     rcx, r12
0x18007a4aa  jz      loc_18007A73D
0x18007a4b0  test    [rcx+1Ch], r15d
0x18007a4b4  jz      loc_18007A73D
0x18007a4ba  cmp     byte ptr [rcx+19h], 2
0x18007a4be  jb      loc_18007A73D
0x18007a4c4  mov     edx, 62h ; 'b'
0x18007a4c9  mov     rcx, [rcx+10h]
0x18007a4cd  mov     r9d, eax
0x18007a4d0  mov     r8, r13
0x18007a4d3  call    WPP_SF_d
0x18007a4d8  jmp     loc_18007A73D
0x18007a4dd  mov     rax, [rsi]
0x18007a4e0  lea     r8, [rbp+arg_18]
0x18007a4e4  mov     dl, 1
0x18007a4e6  mov     [rbp+arg_18], 0
0x18007a4ee  mov     rcx, rsi
0x18007a4f1  mov     rax, [rax+68h]
0x18007a4f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a4fa  mov     ebx, eax
0x18007a4fc  test    eax, eax
0x18007a4fe  jz      short loc_18007A52B
0x18007a500  mov     rcx, cs:WPP_GLOBAL_Control
0x18007a507  cmp     rcx, r12
0x18007a50a  jz      loc_18007A73D
0x18007a510  test    [rcx+1Ch], r15d
0x18007a514  jz      loc_18007A73D
0x18007a51a  cmp     byte ptr [rcx+19h], 2
0x18007a51e  jb      loc_18007A73D
0x18007a524  mov     edx, 63h ; 'c'
0x18007a529  jmp     short loc_18007A4C9
0x18007a52b  mov     rcx, [rbp+arg_18]
0x18007a52f  lea     r9, [rbp+arg_10]
0x18007a533  mov     [rbp+arg_10], 0
0x18007a53a  lea     r8, [rbp+var_30]
0x18007a53e  mov     [rbp+var_30], 0
0x18007a546  mov     edx, 1
0x18007a54b  mov     rax, [rcx]
0x18007a54e  mov     rax, [rax+18h]
0x18007a552  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a557  mov     ebx, eax
0x18007a559  test    eax, eax
0x18007a55b  js      loc_18007A6F4
0x18007a561  cmp     [rbp+arg_10], 0
0x18007a565  jz      loc_18007A6F0
0x18007a56b  mov     rcx, [rbp+var_30]
0x18007a56f  lea     rdx, [rbp+var_28]
0x18007a573  mov     [rbp+var_28], 0
0x18007a57b  mov     rax, [rcx]
0x18007a57e  mov     rax, [rax+20h]
0x18007a582  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a587  mov     rcx, [rbp+var_30]
0x18007a58b  mov     ebx, eax
0x18007a58d  mov     rax, [rcx]
0x18007a590  mov     rax, [rax+10h]
0x18007a594  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a599  test    ebx, ebx
0x18007a59b  jnz     loc_18007A6D1
0x18007a5a1  mov     rcx, [rbp+var_28]
0x18007a5a5  lea     rdx, [rbp+pv]
0x18007a5a9  mov     [rbp+pv], 0
0x18007a5b1  mov     rax, [rcx]
0x18007a5b4  mov     rax, [rax+58h]
0x18007a5b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a5bd  mov     rcx, [rbp+var_28]
0x18007a5c1  mov     ebx, eax
0x18007a5c3  mov     rax, [rcx]
0x18007a5c6  mov     rax, [rax+10h]
0x18007a5ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a5cf  test    ebx, ebx
0x18007a5d1  jnz     loc_18007A6AF
0x18007a5d7  mov     rcx, [rbp+pv]; pv
0x18007a5db  movups  xmm6, xmmword ptr [rcx]
0x18007a5de  call    cs:__imp_CoTaskMemFree
0x18007a5e4  mov     rcx, [rdi]
0x18007a5e7  movdqa  xmm0, xmm6
0x18007a5eb  psrldq  xmm0, 8
0x18007a5f0  mov     [rbp+pv], 0
0x18007a5f8  cmp     rcx, rdi
0x18007a5fb  jz      short loc_18007A61F
0x18007a5fd  movq    rax, xmm6
0x18007a602  sub     rax, [rcx+10h]
0x18007a606  jnz     short loc_18007A611
0x18007a608  movq    rax, xmm0
0x18007a60d  sub     rax, [rcx+18h]
0x18007a611  test    rax, rax
0x18007a614  jz      loc_18007A52B
0x18007a61a  mov     rcx, [rcx]
0x18007a61d  jmp     short loc_18007A5F8
0x18007a61f  call    cs:__imp_GetProcessHeap
0x18007a625  mov     edx, 8; dwFlags
0x18007a62a  mov     rcx, rax; hHeap
0x18007a62d  lea     r8d, [rdx+18h]; dwBytes
0x18007a631  call    cs:__imp_HeapAlloc
0x18007a637  test    rax, rax
0x18007a63a  jz      short loc_18007A673
0x18007a63c  mov     qword ptr [rax], 0
0x18007a643  mov     qword ptr [rax+8], 0
0x18007a64b  movdqu  xmmword ptr [rax+10h], xmm6
0x18007a650  mov     rcx, [rdi+8]
0x18007a654  cmp     [rcx], rdi
0x18007a657  jnz     short loc_18007A66C
0x18007a659  mov     [rax], rdi
0x18007a65c  mov     [rax+8], rcx
0x18007a660  mov     [rcx], rax
0x18007a663  mov     [rdi+8], rax
0x18007a667  jmp     loc_18007A52B
0x18007a66c  mov     ecx, 3
0x18007a671  int     29h; Win8: RtlFailFast(ecx)
0x18007a673  mov     ebx, 8007000Eh
0x18007a678  mov     rcx, cs:WPP_GLOBAL_Control
0x18007a67f  cmp     rcx, r12
0x18007a682  jz      loc_18007A720
0x18007a688  test    [rcx+1Ch], r15d
0x18007a68c  jz      loc_18007A720
0x18007a692  cmp     byte ptr [rcx+19h], 2
0x18007a696  jb      loc_18007A720
0x18007a69c  mov     rcx, [rcx+10h]
0x18007a6a0  mov     edx, 67h ; 'g'
0x18007a6a5  mov     r8, r13
0x18007a6a8  call    WPP_SF_
0x18007a6ad  jmp     short loc_18007A720
0x18007a6af  mov     rcx, cs:WPP_GLOBAL_Control
0x18007a6b6  cmp     rcx, r12
0x18007a6b9  jz      short loc_18007A720
0x18007a6bb  test    [rcx+1Ch], r15d
0x18007a6bf  jz      short loc_18007A720
0x18007a6c1  cmp     byte ptr [rcx+19h], 2
0x18007a6c5  jb      short loc_18007A720
0x18007a6c7  mov     edx, 66h ; 'f'
0x18007a6cc  mov     r9d, ebx
0x18007a6cf  jmp     short loc_18007A714
0x18007a6d1  mov     rcx, cs:WPP_GLOBAL_Control
0x18007a6d8  cmp     rcx, r12
0x18007a6db  jz      short loc_18007A720
0x18007a6dd  test    [rcx+1Ch], r15d
0x18007a6e1  jz      short loc_18007A720
0x18007a6e3  cmp     byte ptr [rcx+19h], 2
0x18007a6e7  jb      short loc_18007A720
0x18007a6e9  mov     edx, 65h ; 'e'
0x18007a6ee  jmp     short loc_18007A6CC
0x18007a6f0  xor     ebx, ebx
0x18007a6f2  jmp     short loc_18007A720
0x18007a6f4  mov     rcx, cs:WPP_GLOBAL_Control
0x18007a6fb  cmp     rcx, r12
0x18007a6fe  jz      short loc_18007A720
0x18007a700  test    [rcx+1Ch], r15d
0x18007a704  jz      short loc_18007A720
0x18007a706  cmp     byte ptr [rcx+19h], 2
0x18007a70a  jb      short loc_18007A720
0x18007a70c  mov     edx, 64h ; 'd'
0x18007a711  mov     r9d, eax
0x18007a714  mov     rcx, [rcx+10h]
0x18007a718  mov     r8, r13
0x18007a71b  call    WPP_SF_d
0x18007a720  mov     rcx, [rbp+arg_18]
0x18007a724  test    rcx, rcx
0x18007a727  jz      short loc_18007A73D
0x18007a729  mov     rax, [rcx]
0x18007a72c  mov     rax, [rax+10h]
0x18007a730  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a735  mov     [rbp+arg_18], 0
0x18007a73d  call    cs:__imp_CoUninitialize
0x18007a743  mov     rcx, cs:WPP_GLOBAL_Control
0x18007a74a  cmp     rcx, r12
0x18007a74d  jz      short loc_18007A76F
0x18007a74f  test    [rcx+1Ch], r15d
0x18007a753  jz      short loc_18007A76F
0x18007a755  cmp     byte ptr [rcx+19h], 6
0x18007a759  jb      short loc_18007A76F
0x18007a75b  mov     rcx, [rcx+10h]
0x18007a75f  mov     edx, 68h ; 'h'
0x18007a764  mov     r9d, ebx
0x18007a767  mov     r8, r13
0x18007a76a  call    WPP_SF_d
0x18007a76f  movaps  xmm6, [rsp+60h+var_10]
0x18007a774  lea     r11, [rsp+60h+var_s0]
0x18007a779  mov     rsi, [r11+38h]
0x18007a77d  mov     eax, ebx
0x18007a77f  mov     rbx, [r11+30h]
0x18007a783  mov     rsp, r11
0x18007a786  pop     r15
0x18007a788  pop     r13
0x18007a78a  pop     r12
0x18007a78c  pop     rdi
0x18007a78d  pop     rbp
0x18007a78e  retn
```
