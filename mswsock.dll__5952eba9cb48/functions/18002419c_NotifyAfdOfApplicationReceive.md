# NotifyAfdOfApplicationReceive

- ea: `0x18002419c`
- end: `0x1800243d6`
- name: `NotifyAfdOfApplicationReceive`
- size: `570`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18004abd0`
- `0x18004b890`

## callees

- `0x1800214a0`
- `0x18002419c`
- `0x180025288`
- `0x180038e30`
- `0x18003ae8c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800243bc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800243bc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800241f3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800241f3`

## string_xrefs

- `0x1800242b7`: `AfdReadMore`
- `0x1800242ab`: `AfdNothingToRead`
- `0x180024386`: `AfdReadMoreOob`
- `0x18002437a`: `AfdNothingToReadOob`

## pseudocode

```c
void __fastcall NotifyAfdOfApplicationReceive(__int64 *a1, int a2)
{
  unsigned int *v4; // rdi
  int *v5; // r8
  unsigned int v6; // edi
  HANDLE v7; // rcx
  __int64 v8; // r9
  int v9; // ett
  int v10; // eax
  __int64 v11; // rax
  const char *v12; // r9
  __int64 v13; // rdx
  int *v14; // r8
  HANDLE v15; // r9
  __int64 v16; // rdx
  int v17; // ett
  int v18; // eax
  __int64 v19; // rax
  const char *v20; // r9
  __int64 v21; // [rsp+30h] [rbp-28h] BYREF
  __int64 v22; // [rsp+38h] [rbp-20h]
  __int64 v23; // [rsp+40h] [rbp-18h]

  if ( a2 )
  {
    if ( !*((_DWORD *)a1 + 31) || *(_DWORD *)(a1[27] + 32) )
    {
      v4 = (unsigned int *)(a1 + 15);
      goto LABEL_7;
    }
  }
  else
  {
    v4 = (unsigned int *)(a1 + 15);
    if ( !*((_DWORD *)a1 + 30) || *(_DWORD *)(a1[27] + 28) )
    {
LABEL_7:
      EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 6));
      if ( !a2 )
      {
        v6 = *v4;
        if ( v6 || *((_DWORD *)a1 + 154) )
        {
          if ( *(int *)(a1[27] + 28) > 0 )
          {
            v11 = *a1;
            v22 = a1[27] + 24;
            v23 = 0;
            v21 = *(_QWORD *)(v11 + 8);
            v10 = AfdSetEvent(SockSanHelperHandle, &v21);
            goto LABEL_17;
          }
        }
        else
        {
          v7 = SockSanHelperHandle;
          v5 = (int *)(a1[27] + 24);
          v8 = *(_QWORD *)(*a1 + 8);
          _m_prefetchw(v5);
          do
            v9 = *v5;
          while ( v9 != _InterlockedCompareExchange(v5, *v5 & 0xFFFFFFFE, *v5) );
          if ( v5[1] > 0 )
          {
            v23 = 0;
            v21 = v8;
            v22 = (__int64)v5;
            v10 = AfdResetEvent(v7, &v21);
            goto LABEL_17;
          }
        }
        v10 = 0;
LABEL_17:
        if ( v10 < 0 && (xmmword_180063D60 & 2) != 0 )
        {
          v12 = "AfdReadMore";
          if ( !v6 )
            v12 = "AfdNothingToRead";
          WPP_SF_sD((unsigned int)"AfdNothingToRead", 245, (_DWORD)v5, (_DWORD)v12, v10);
        }
        if ( (BYTE1(xmmword_180063D60) & 8) == 0 )
          goto LABEL_40;
        v13 = 246;
LABEL_39:
        WPP_SF_d(1035, v13, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids, v6);
LABEL_40:
        LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 6));
        return;
      }
      v6 = *((_DWORD *)a1 + 31);
      v14 = (int *)(a1[27] + 24);
      if ( v6 )
      {
        if ( *(int *)(a1[27] + 32) > 0 )
        {
          v19 = *a1;
          v23 = 1;
          v22 = (__int64)v14;
          v21 = *(_QWORD *)(v19 + 8);
          v18 = AfdSetEvent(SockSanHelperHandle, &v21);
          goto LABEL_32;
        }
      }
      else
      {
        v15 = SockSanHelperHandle;
        v16 = *(_QWORD *)(*a1 + 8);
        _m_prefetchw(v14);
        do
          v17 = *v14;
        while ( v17 != _InterlockedCompareExchange(v14, *v14 & 0xFFFFFFFD, *v14) );
        if ( v14[2] > 0 )
        {
          v21 = v16;
          v23 = 1;
          v22 = (__int64)v14;
          v18 = AfdResetEvent(v15, &v21);
          goto LABEL_32;
        }
      }
      v18 = 0;
LABEL_32:
      if ( v18 < 0 && (xmmword_180063D60 & 2) != 0 )
      {
        v20 = "AfdReadMoreOob";
        if ( !v6 )
          v20 = "AfdNothingToReadOob";
        WPP_SF_sD((unsigned int)"AfdNothingToReadOob", 247, (_DWORD)v14, (_DWORD)v20, v18);
      }
      if ( (BYTE1(xmmword_180063D60) & 8) == 0 )
        goto LABEL_40;
      v13 = 248;
      goto LABEL_39;
    }
  }
}

```

## disassembly

```asm
0x18002419c  push    rbp
0x18002419e  push    rbx
0x18002419f  push    rsi
0x1800241a0  push    rdi
0x1800241a1  push    r14
0x1800241a3  push    r15
0x1800241a5  mov     rbp, rsp
0x1800241a8  sub     rsp, 58h
0x1800241ac  xor     r15d, r15d
0x1800241af  mov     esi, edx
0x1800241b1  mov     rbx, rcx
0x1800241b4  test    edx, edx
0x1800241b6  jz      short loc_1800241D5
0x1800241b8  cmp     [rcx+7Ch], r15d
0x1800241bc  jz      short loc_1800241CF
0x1800241be  mov     rax, [rcx+0D8h]
0x1800241c5  cmp     [rax+20h], r15d
0x1800241c9  jz      loc_1800243C8
0x1800241cf  lea     rdi, [rcx+78h]
0x1800241d3  jmp     short loc_1800241EF
0x1800241d5  lea     rdi, [rcx+78h]
0x1800241d9  cmp     [rdi], r15d
0x1800241dc  jz      short loc_1800241EF
0x1800241de  mov     rax, [rcx+0D8h]
0x1800241e5  cmp     [rax+1Ch], r15d
0x1800241e9  jz      loc_1800243C8
0x1800241ef  add     rcx, 30h ; '0'; lpCriticalSection
0x1800241f3  call    cs:__imp_EnterCriticalSection
0x1800241fa  nop     dword ptr [rax+rax+00h]
0x1800241ff  test    esi, esi
0x180024201  jnz     loc_1800242DE
0x180024207  mov     edi, [rdi]
0x180024209  test    edi, edi
0x18002420b  jnz     short loc_18002425F
0x18002420d  cmp     [rbx+268h], r15d
0x180024214  jnz     short loc_18002425F
0x180024216  mov     rax, [rbx]
0x180024219  mov     r8, [rbx+0D8h]
0x180024220  mov     rcx, cs:SockSanHelperHandle
0x180024227  add     r8, 18h
0x18002422b  mov     r9, [rax+8]
0x18002422f  prefetchw byte ptr [r8]
0x180024233  mov     eax, [r8]
0x180024236  mov     edx, eax
0x180024238  and     edx, 0FFFFFFFEh
0x18002423b  lock cmpxchg [r8], edx
0x180024240  jnz     short loc_180024233
0x180024242  cmp     [r8+4], r15d
0x180024246  jle     short loc_180024295
0x180024248  lea     rdx, [rbp+var_28]
0x18002424c  mov     [rbp+var_18], r15
0x180024250  mov     [rbp+var_28], r9
0x180024254  mov     [rbp+var_20], r8
0x180024258  call    AfdResetEvent
0x18002425d  jmp     short loc_180024298
0x18002425f  mov     rcx, [rbx+0D8h]
0x180024266  add     rcx, 18h
0x18002426a  cmp     [rcx+4], r15d
0x18002426e  jle     short loc_180024295
0x180024270  mov     rax, [rbx]
0x180024273  mov     [rbp+var_20], rcx
0x180024277  mov     rcx, cs:SockSanHelperHandle
0x18002427e  mov     [rbp+var_18], r15
0x180024282  mov     rdx, [rax+8]
0x180024286  mov     [rbp+var_28], rdx
0x18002428a  lea     rdx, [rbp+var_28]
0x18002428e  call    AfdSetEvent
0x180024293  jmp     short loc_180024298
0x180024295  mov     eax, r15d
0x180024298  test    eax, eax
0x18002429a  jns     short loc_1800242C7
0x18002429c  test    byte ptr cs:xmmword_180063D60, 2
0x1800242a3  jz      short loc_1800242C7
0x1800242a5  test    edi, edi
0x1800242a7  mov     [rsp+58h+var_38], eax
0x1800242ab  lea     rcx, aAfdnothingtore; "AfdNothingToRead"
0x1800242b2  mov     edx, 0F5h
0x1800242b7  lea     r9, aAfdreadmore; "AfdReadMore"
0x1800242be  cmovz   r9, rcx
0x1800242c2  call    WPP_SF_sD
0x1800242c7  test    byte ptr cs:xmmword_180063D60+1, 8
0x1800242ce  jz      loc_1800243B8
0x1800242d4  mov     edx, 0F6h
0x1800242d9  jmp     loc_1800243A4
0x1800242de  mov     r8, [rbx+0D8h]
0x1800242e5  mov     edi, [rbx+7Ch]
0x1800242e8  add     r8, 18h
0x1800242ec  test    edi, edi
0x1800242ee  jnz     short loc_180024335
0x1800242f0  mov     rax, [rbx]
0x1800242f3  mov     r9, cs:SockSanHelperHandle
0x1800242fa  mov     rdx, [rax+8]
0x1800242fe  prefetchw byte ptr [r8]
0x180024302  mov     eax, [r8]
0x180024305  mov     ecx, eax
0x180024307  and     ecx, 0FFFFFFFDh
0x18002430a  lock cmpxchg [r8], ecx
0x18002430f  jnz     short loc_180024302
0x180024311  cmp     [r8+8], r15d
0x180024315  jle     short loc_180024364
0x180024317  mov     [rbp+var_28], rdx
0x18002431b  mov     rcx, r9
0x18002431e  lea     rdx, [rbp+var_28]
0x180024322  mov     [rbp+var_18], 1
0x18002432a  mov     [rbp+var_20], r8
0x18002432e  call    AfdResetEvent
0x180024333  jmp     short loc_180024367
0x180024335  cmp     [r8+8], r15d
0x180024339  jle     short loc_180024364
0x18002433b  mov     rax, [rbx]
0x18002433e  mov     rcx, cs:SockSanHelperHandle
0x180024345  mov     [rbp+var_18], 1
0x18002434d  mov     [rbp+var_20], r8
0x180024351  mov     rdx, [rax+8]
0x180024355  mov     [rbp+var_28], rdx
0x180024359  lea     rdx, [rbp+var_28]
0x18002435d  call    AfdSetEvent
0x180024362  jmp     short loc_180024367
0x180024364  mov     eax, r15d
0x180024367  test    eax, eax
0x180024369  jns     short loc_180024396
0x18002436b  test    byte ptr cs:xmmword_180063D60, 2
0x180024372  jz      short loc_180024396
0x180024374  test    edi, edi
0x180024376  mov     [rsp+58h+var_38], eax
0x18002437a  lea     rcx, aAfdnothingtore_0; "AfdNothingToReadOob"
0x180024381  mov     edx, 0F7h
0x180024386  lea     r9, aAfdreadmoreoob; "AfdReadMoreOob"
0x18002438d  cmovz   r9, rcx
0x180024391  call    WPP_SF_sD
0x180024396  test    byte ptr cs:xmmword_180063D60+1, 8
0x18002439d  jz      short loc_1800243B8
0x18002439f  mov     edx, 0F8h
0x1800243a4  mov     r9d, edi
0x1800243a7  lea     r8, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids
0x1800243ae  mov     ecx, 40Bh
0x1800243b3  call    WPP_SF_d
0x1800243b8  lea     rcx, [rbx+30h]; lpCriticalSection
0x1800243bc  call    cs:__imp_LeaveCriticalSection
0x1800243c3  nop     dword ptr [rax+rax+00h]
0x1800243c8  add     rsp, 58h
0x1800243cc  pop     r15
0x1800243ce  pop     r14
0x1800243d0  pop     rdi
0x1800243d1  pop     rsi
0x1800243d2  pop     rbx
0x1800243d3  pop     rbp
0x1800243d4  retn
```
