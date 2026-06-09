# PrjfCompleteCommandHandler

- ea: `0x14000420c`
- end: `0x140004631`
- name: `PrjfCompleteCommandHandler`
- size: `1061`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140031a00`

## callees

- `0x140003e6c`
- `0x14000420c`
- `0x14000bb80`
- `0x14000d008`
- `0x14000d128`
- `0x140010e3c`
- `0x140010f1c`
- `0x140021f8c`

## import_xrefs

- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x140004499`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x140004499`
- `ntoskrnl!KeSetEvent` at `0x1400045f5`
- `ntoskrnl!KeSetEvent` at `0x1400045f5`
- `HAL!KeQueryPerformanceCounter` at `0x140004445`
- `HAL!KeQueryPerformanceCounter` at `0x140004479`
- `HAL!KeQueryPerformanceCounter` at `0x140004445`
- `HAL!KeQueryPerformanceCounter` at `0x140004479`
- `FLTMGR!FltReleaseResource` at `0x140004604`
- `FLTMGR!FltReleaseResource` at `0x140004604`
- `FLTMGR!FltAcquireResourceShared` at `0x140004419`
- `FLTMGR!FltAcquireResourceShared` at `0x140004419`

## pseudocode

```c
void __fastcall PrjfCompleteCommandHandler(__int64 a1, unsigned int *a2)
{
  unsigned int v3; // edx
  int v4; // r8d
  unsigned int v5; // eax
  int v6; // edx
  __int64 UnionContextByVirtualizationInstanceInfo; // rsi
  int v8; // r8d
  LARGE_INTEGER v9; // rbx
  LONGLONG v10; // rbp
  volatile signed __int32 *v11; // rax
  int v12; // edx
  int v13; // r8d
  PRKEVENT *v14; // rbx
  __int64 v15; // rcx
  unsigned int v16; // edx
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // r9
  __int128 Buffer; // [rsp+70h] [rbp-28h] BYREF
  union _LARGE_INTEGER PerformanceFrequency; // [rsp+A8h] [rbp+10h] BYREF

  v3 = *a2;
  v4 = a1;
  Buffer = 0;
  if ( v3 < 0x64 )
  {
    if ( (BYTE1(xmmword_14001A3D0) & 0x40) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v3) = BYTE1(xmmword_14001A3D0) & 0x40;
      LOBYTE(v4) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sDL(
        526,
        v3,
        v4,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        14,
        64,
        (__int64)&WPP_c505924bdc6333f282870af0a028ded4_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\message.c",
        217,
        13);
    }
    return;
  }
  v5 = a2[24];
  if ( v5 + 100 < v5 )
  {
    if ( (BYTE1(xmmword_14001A3D0) & 0x40) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v3) = BYTE1(xmmword_14001A3D0) & 0x40;
      LOBYTE(v4) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sDL(
        526,
        v3,
        v4,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        14,
        65,
        (__int64)&WPP_c505924bdc6333f282870af0a028ded4_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\message.c",
        229,
        13);
    }
    return;
  }
  if ( v3 < v5 + 100 )
  {
    if ( (BYTE1(xmmword_14001A3D0) & 0x40) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v3) = BYTE1(xmmword_14001A3D0) & 0x40;
      LOBYTE(v4) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sDL(
        526,
        v3,
        v4,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        14,
        66,
        (__int64)&WPP_c505924bdc6333f282870af0a028ded4_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\message.c",
        236,
        13);
    }
    return;
  }
  UnionContextByVirtualizationInstanceInfo = PrjfGetUnionContextByVirtualizationInstanceInfo(a2 + 2, a1);
  if ( UnionContextByVirtualizationInstanceInfo )
  {
    LODWORD(Buffer) = a2[22];
    FltAcquireResourceShared((PERESOURCE)(UnionContextByVirtualizationInstanceInfo + 312));
    if ( (*(_DWORD *)(UnionContextByVirtualizationInstanceInfo + 800) & 0x800) != 0 )
    {
      PerformanceFrequency.QuadPart = 0;
      v9 = KeQueryPerformanceCounter(&PerformanceFrequency);
      v10 = PerformanceFrequency.QuadPart / 10;
      while ( *(_QWORD *)&KeQueryPerformanceCounter(0) - v9.QuadPart < v10 )
        ;
    }
    v11 = (volatile signed __int32 *)RtlLookupElementGenericTableAvl(
                                       (PRTL_AVL_TABLE)(UnionContextByVirtualizationInstanceInfo + 416),
                                       &Buffer);
    v14 = (PRKEVENT *)v11;
    if ( v11 )
    {
      if ( _InterlockedCompareExchange(v11 + 1, 2, 1) == 1 )
      {
        v15 = *((_QWORD *)v11 + 1);
        if ( a2[24] <= *(_DWORD *)(v15 + 28) )
        {
          *(_DWORD *)(v15 + 24) = a2[23];
          v16 = a2[24];
          if ( v16 )
          {
            *(_DWORD *)(*((_QWORD *)v11 + 1) + 28LL) = v16;
            memmove(*(void **)(*((_QWORD *)v11 + 1) + 32LL), a2 + 25, a2[24]);
          }
        }
        else
        {
          *(_DWORD *)(v15 + 24) = -1073741789;
          *(_DWORD *)(*((_QWORD *)v11 + 1) + 28LL) = a2[24];
          if ( (BYTE1(xmmword_14001A3D0) & 0x40) != 0
            || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v12) = BYTE1(xmmword_14001A3D0) & 0x40;
            LOBYTE(v13) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
            WPP_RECORDER_AND_TRACE_SF_sDlLL(
              *(_DWORD *)(*((_QWORD *)v11 + 1) + 28LL),
              v12,
              v13,
              *((_QWORD *)WPP_GLOBAL_Control + 8));
          }
        }
        KeSetEvent(v14[1], 0, 0);
        goto LABEL_35;
      }
      LOBYTE(v13) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      LOBYTE(v12) = BYTE9(xmmword_14001A3D0) & 0x40;
      if ( (BYTE9(xmmword_14001A3D0) & 0x40) == 0 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
LABEL_35:
        FltReleaseResource((PERESOURCE)(UnionContextByVirtualizationInstanceInfo + 312));
        PrjfReleaseUnionContext((char *)UnionContextByVirtualizationInstanceInfo, v17, v18, v19);
        return;
      }
    }
    else
    {
      LOBYTE(v13) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      LOBYTE(v12) = BYTE9(xmmword_14001A3D0) & 0x40;
      if ( (BYTE9(xmmword_14001A3D0) & 0x40) == 0 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_35;
    }
    WPP_RECORDER_AND_TRACE_SF_sDl(
      (unsigned int)&WPP_RECORDER_INITIALIZED,
      v12,
      v13,
      *((_QWORD *)WPP_GLOBAL_Control + 8));
    goto LABEL_35;
  }
  if ( (BYTE1(xmmword_14001A3D0) & 0x40) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v6) = BYTE1(xmmword_14001A3D0) & 0x40;
    LOBYTE(v8) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_sD(
      526,
      v6,
      v8,
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      2,
      14,
      67,
      (__int64)&WPP_c505924bdc6333f282870af0a028ded4_Traceguids,
      (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\message.c",
      249);
  }
}

```

## disassembly

```asm
0x14000420c  mov     [rsp+arg_0], rbx
0x140004211  mov     [rsp+arg_10], rbp
0x140004216  push    rsi
0x140004217  push    rdi
0x140004218  push    r14
0x14000421a  sub     rsp, 80h
0x140004221  mov     rdi, rdx
0x140004224  xorps   xmm0, xmm0
0x140004227  mov     edx, [rdx]
0x140004229  mov     r8, rcx
0x14000422c  movups  [rsp+98h+Buffer], xmm0
0x140004231  cmp     edx, 64h ; 'd'
0x140004234  jnb     short loc_1400042B4
0x140004236  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x14000423c  lea     rcx, WPP_RECORDER_INITIALIZED
0x140004243  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14000424a  mov     eax, 40h ; '@'
0x14000424f  setnz   r8b
0x140004253  and     dl, al
0x140004255  jnz     short loc_140004260
0x140004257  test    r8b, r8b
0x14000425a  jz      loc_140004618
0x140004260  mov     [rsp+98h+var_48], 0C000000Dh
0x140004268  lea     r9, aOnecoreBaseFsG_5; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14000426f  mov     [rsp+98h+var_50], 6D9h
0x140004277  mov     [rsp+98h+var_58], r9
0x14000427c  lea     r9, WPP_c505924bdc6333f282870af0a028ded4_Traceguids
0x140004283  mov     [rsp+98h+var_60], r9
0x140004288  mov     [rsp+98h+var_68], ax
0x14000428d  mov     r9, cs:WPP_GLOBAL_Control
0x140004294  mov     ecx, 20Eh
0x140004299  mov     [rsp+98h+var_70], 0Eh
0x1400042a1  mov     [rsp+98h+var_78], 2
0x1400042a6  mov     r9, [r9+40h]
0x1400042aa  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x1400042af  jmp     loc_140004618
0x1400042b4  mov     eax, [rdi+60h]
0x1400042b7  lea     ecx, [rax+64h]
0x1400042ba  cmp     ecx, eax
0x1400042bc  jnb     short loc_14000431C
0x1400042be  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x1400042c4  lea     rcx, WPP_RECORDER_INITIALIZED
0x1400042cb  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1400042d2  mov     eax, 40h ; '@'
0x1400042d7  setnz   r8b
0x1400042db  and     dl, al
0x1400042dd  jnz     short loc_1400042E8
0x1400042df  test    r8b, r8b
0x1400042e2  jz      loc_140004618
0x1400042e8  mov     [rsp+98h+var_48], 0C000000Dh
0x1400042f0  lea     r9, aOnecoreBaseFsG_5; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x1400042f7  mov     [rsp+98h+var_50], 6E5h
0x1400042ff  mov     [rsp+98h+var_58], r9
0x140004304  lea     r9, WPP_c505924bdc6333f282870af0a028ded4_Traceguids
0x14000430b  mov     [rsp+98h+var_60], r9
0x140004310  mov     [rsp+98h+var_68], 41h ; 'A'
0x140004317  jmp     loc_14000428D
0x14000431c  cmp     edx, ecx
0x14000431e  jnb     short loc_14000437E
0x140004320  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x140004326  lea     rcx, WPP_RECORDER_INITIALIZED
0x14000432d  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140004334  mov     eax, 40h ; '@'
0x140004339  setnz   r8b
0x14000433d  and     dl, al
0x14000433f  jnz     short loc_14000434A
0x140004341  test    r8b, r8b
0x140004344  jz      loc_140004618
0x14000434a  mov     [rsp+98h+var_48], 0C000000Dh
0x140004352  lea     r9, aOnecoreBaseFsG_5; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140004359  mov     [rsp+98h+var_50], 6ECh
0x140004361  mov     [rsp+98h+var_58], r9
0x140004366  lea     r9, WPP_c505924bdc6333f282870af0a028ded4_Traceguids
0x14000436d  mov     [rsp+98h+var_60], r9
0x140004372  mov     [rsp+98h+var_68], 42h ; 'B'
0x140004379  jmp     loc_14000428D
0x14000437e  lea     rcx, [rdi+8]
0x140004382  mov     rdx, r8
0x140004385  call    PrjfGetUnionContextByVirtualizationInstanceInfo
0x14000438a  mov     rsi, rax
0x14000438d  test    rax, rax
0x140004390  jnz     short loc_140004408
0x140004392  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x140004398  lea     rcx, WPP_RECORDER_INITIALIZED
0x14000439f  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1400043a6  lea     eax, [rsi+40h]
0x1400043a9  setnz   r8b
0x1400043ad  and     dl, al
0x1400043af  jnz     short loc_1400043BA
0x1400043b1  test    r8b, r8b
0x1400043b4  jz      loc_140004618
0x1400043ba  mov     [rsp+98h+var_50], 6F9h
0x1400043c2  lea     r9, aOnecoreBaseFsG_5; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x1400043c9  mov     [rsp+98h+var_58], r9
0x1400043ce  mov     ecx, 20Eh
0x1400043d3  lea     r9, WPP_c505924bdc6333f282870af0a028ded4_Traceguids
0x1400043da  mov     [rsp+98h+var_60], r9
0x1400043df  mov     r9, cs:WPP_GLOBAL_Control
0x1400043e6  mov     [rsp+98h+var_68], 43h ; 'C'
0x1400043ed  mov     [rsp+98h+var_70], 0Eh
0x1400043f5  mov     [rsp+98h+var_78], 2
0x1400043fa  mov     r9, [r9+40h]
0x1400043fe  call    WPP_RECORDER_AND_TRACE_SF_sD
0x140004403  jmp     loc_140004618
0x140004408  mov     eax, [rdi+58h]
0x14000440b  lea     r14, [rsi+138h]
0x140004412  mov     rcx, r14; Resource
0x140004415  mov     dword ptr [rsp+98h+Buffer], eax
0x140004419  call    cs:__imp_FltAcquireResourceShared
0x140004420  nop     dword ptr [rax+rax+00h]
0x140004425  test    dword ptr [rsi+320h], 800h
0x14000442f  jz      short loc_14000448D
0x140004431  lea     rcx, [rsp+98h+PerformanceFrequency]; PerformanceFrequency
0x140004439  mov     qword ptr [rsp+98h+PerformanceFrequency], 0
0x140004445  call    cs:__imp_KeQueryPerformanceCounter
0x14000444c  nop     dword ptr [rax+rax+00h]
0x140004451  mov     rbx, rax
0x140004454  mov     rax, 6666666666666667h
0x14000445e  imul    qword ptr [rsp+98h+PerformanceFrequency]
0x140004466  mov     rbp, rdx
0x140004469  sar     rbp, 2
0x14000446d  mov     rax, rbp
0x140004470  shr     rax, 3Fh
0x140004474  add     rbp, rax
0x140004477  xor     ecx, ecx; PerformanceFrequency
0x140004479  call    cs:__imp_KeQueryPerformanceCounter
0x140004480  nop     dword ptr [rax+rax+00h]
0x140004485  sub     rax, rbx
0x140004488  cmp     rax, rbp
0x14000448b  jl      short loc_140004477
0x14000448d  lea     rcx, [rsi+1A0h]; Table
0x140004494  lea     rdx, [rsp+98h+Buffer]; Buffer
0x140004499  call    cs:__imp_RtlLookupElementGenericTableAvl
0x1400044a0  nop     dword ptr [rax+rax+00h]
0x1400044a5  mov     rbx, rax
0x1400044a8  test    rax, rax
0x1400044ab  jnz     short loc_140004501
0x1400044ad  mov     dl, byte ptr cs:xmmword_14001A3D0+9
0x1400044b3  lea     rcx, WPP_RECORDER_INITIALIZED
0x1400044ba  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1400044c1  lea     eax, [rbx+40h]
0x1400044c4  setnz   r8b
0x1400044c8  and     dl, al
0x1400044ca  jnz     short loc_1400044D5
0x1400044cc  test    r8b, r8b
0x1400044cf  jz      loc_140004601
0x1400044d5  mov     eax, dword ptr [rsp+98h+Buffer]
0x1400044d9  mov     [rsp+98h+var_48], eax
0x1400044dd  mov     [rsp+98h+var_50], 72Ch
0x1400044e5  mov     [rsp+98h+var_68], 44h ; 'D'
0x1400044ec  mov     r9, cs:WPP_GLOBAL_Control
0x1400044f3  mov     r9, [r9+40h]
0x1400044f7  call    WPP_RECORDER_AND_TRACE_SF_sDl
0x1400044fc  jmp     loc_140004601
0x140004501  mov     eax, 1
0x140004506  lea     r9d, [rax+1]
0x14000450a  lock cmpxchg [rbx+4], r9d
0x140004510  jz      short loc_140004554
0x140004512  mov     dl, byte ptr cs:xmmword_14001A3D0+9
0x140004518  lea     rcx, WPP_RECORDER_INITIALIZED
0x14000451f  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140004526  lea     eax, [r9+3Eh]
0x14000452a  setnz   r8b
0x14000452e  and     dl, al
0x140004530  jnz     short loc_14000453B
0x140004532  test    r8b, r8b
0x140004535  jz      loc_140004601
0x14000453b  mov     eax, dword ptr [rsp+98h+Buffer]
0x14000453f  mov     [rsp+98h+var_48], eax
0x140004543  mov     [rsp+98h+var_50], 742h
0x14000454b  mov     [rsp+98h+var_68], 45h ; 'E'
0x140004552  jmp     short loc_1400044EC
0x140004554  mov     rcx, [rbx+8]
0x140004558  mov     eax, [rcx+1Ch]
0x14000455b  cmp     [rdi+60h], eax
0x14000455e  jbe     short loc_1400045C3
0x140004560  mov     dword ptr [rcx+18h], 0C0000023h
0x140004567  mov     rcx, [rbx+8]
0x14000456b  mov     eax, [rdi+60h]
0x14000456e  mov     [rcx+1Ch], eax
0x140004571  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x140004577  lea     rcx, WPP_RECORDER_INITIALIZED
0x14000457e  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140004585  mov     eax, 40h ; '@'
0x14000458a  setnz   r8b
0x14000458e  and     dl, al
0x140004590  jnz     short loc_140004597
0x140004592  test    r8b, r8b
0x140004595  jz      short loc_1400045EC
0x140004597  mov     rax, [rbx+8]
0x14000459b  mov     r9, cs:WPP_GLOBAL_Control
0x1400045a2  mov     ecx, [rax+1Ch]
0x1400045a5  mov     eax, [rdi+60h]
0x1400045a8  mov     r9, [r9+40h]
0x1400045ac  mov     [rsp+98h+var_38], ecx
0x1400045b0  mov     [rsp+98h+var_40], eax
0x1400045b4  mov     eax, dword ptr [rsp+98h+Buffer]
0x1400045b8  mov     [rsp+98h+var_48], eax
0x1400045bc  call    WPP_RECORDER_AND_TRACE_SF_sDlLL
0x1400045c1  jmp     short loc_1400045EC
0x1400045c3  mov     eax, [rdi+5Ch]
0x1400045c6  mov     [rcx+18h], eax
0x1400045c9  mov     edx, [rdi+60h]
0x1400045cc  test    edx, edx
0x1400045ce  jz      short loc_1400045EC
0x1400045d0  mov     rax, [rbx+8]
0x1400045d4  mov     [rax+1Ch], edx
0x1400045d7  lea     rdx, [rdi+64h]; Src
0x1400045db  mov     rcx, [rbx+8]
0x1400045df  mov     r8d, [rdi+60h]; Size
0x1400045e3  mov     rcx, [rcx+20h]; void *
0x1400045e7  call    memmove
0x1400045ec  mov     rcx, [rbx+8]; Event
0x1400045f0  xor     r8d, r8d; Wait
0x1400045f3  xor     edx, edx; Increment
0x1400045f5  call    cs:__imp_KeSetEvent
0x1400045fc  nop     dword ptr [rax+rax+00h]
0x140004601  mov     rcx, r14; Resource
0x140004604  call    cs:__imp_FltReleaseResource
0x14000460b  nop     dword ptr [rax+rax+00h]
0x140004610  mov     rcx, rsi; P
0x140004613  call    PrjfReleaseUnionContext
0x140004618  lea     r11, [rsp+98h+var_18]
0x140004620  mov     rbx, [r11+20h]
0x140004624  mov     rbp, [r11+30h]
0x140004628  mov     rsp, r11
0x14000462b  pop     r14
0x14000462d  pop     rdi
0x14000462e  pop     rsi
0x14000462f  retn
```
