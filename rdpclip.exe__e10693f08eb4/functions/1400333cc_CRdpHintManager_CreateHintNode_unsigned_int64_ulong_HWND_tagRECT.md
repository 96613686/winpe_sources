# CRdpHintManager::CreateHintNode(unsigned __int64,ulong,HWND__ *,tagRECT *)

- ea: `0x1400333cc`
- end: `0x140033647`
- name: `?CreateHintNode@CRdpHintManager@@AEAAJ_KKPEAUHWND__@@PEAUtagRECT@@@Z`
- size: `635`
- prototype: `__int64 __usercall@<rax>(CRdpHintManager *__hidden this@<rcx>, unsigned __int64@<rdx>, unsigned int@<r8d>, HWND@<r9>, struct tagRECT *)`
- caller_count: `2`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x140034e40`
- `0x140035a70`

## callees

- `0x1400030d3`
- `0x140004b1c`
- `0x1400056c4`
- `0x140005750`
- `0x140011054`
- `0x14001ff80`
- `0x1400333cc`
- `0x140033868`
- `0x140033e40`
- `0x14006a0fa`
- `0x14006a120`

## import_xrefs

- `USER32!GetClassNameW` at `0x14003350b`
- `USER32!GetClassNameW` at `0x14003350b`
- `USER32!CopyRect` at `0x1400335f4`
- `USER32!CopyRect` at `0x1400335f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14003346b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14003346b`

## string_xrefs

- `0x14003349d`: `"CoTaskMemAlloc( TSMM_VIDEO_HINT_NODE )"`

## pseudocode

```c
__int64 __fastcall CRdpHintManager::CreateHintNode(
        CRdpHintManager *this,
        __int64 a2,
        int a3,
        HWND a4,
        struct tagRECT *lprcSrc)
{
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int DesktopScalingFactor; // edi
  char *v11; // rax
  char *v12; // rbx
  unsigned int v13; // eax
  unsigned int v14; // eax
  unsigned int v15; // eax
  _QWORD *v16; // rax
  WCHAR ClassName[128]; // [rsp+30h] [rbp-138h] BYREF

  if ( (unsigned int)CRdpHintManager::HasHintsForWindow(this, a4) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dq(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        66,
        &WPP_7fbfedf3cb2c3dda177afd18a098990f_Traceguids,
        CurrentThreadActivityIdPrefix,
        a4);
    }
    return (unsigned int)-2147024713;
  }
  v11 = (char *)CoTaskMemAlloc(0x908u);
  v12 = v11;
  if ( !v11 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v13 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Ds(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        67,
        (unsigned int)&WPP_7fbfedf3cb2c3dda177afd18a098990f_Traceguids,
        v13,
        (__int64)"\"CoTaskMemAlloc( TSMM_VIDEO_HINT_NODE )\"");
    }
    return (unsigned int)-2147024882;
  }
  memset_0(v11, 0, 0x908u);
  *((_QWORD *)v12 + 2) = a2;
  *((_DWORD *)v12 + 6) = a3;
  *((_QWORD *)v12 + 4) = a4;
  memset_0(ClassName, 0, sizeof(ClassName));
  if ( !GetClassNameW(a4, ClassName, 128)
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    v14 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 68, &WPP_7fbfedf3cb2c3dda177afd18a098990f_Traceguids, v14);
  }
  *((_DWORD *)v12 + 292) = wcscmp_0(ClassName, L"VirtualMMRVideoWindowClass") == 0;
  if ( lprcSrc )
  {
    DesktopScalingFactor = 0;
    *((_DWORD *)v12 + 15) = 1;
    CopyRect((LPRECT)(v12 + 40), lprcSrc);
    goto LABEL_25;
  }
  *((_DWORD *)v12 + 15) = 0;
  DesktopScalingFactor = CRdpHintManager::GetDesktopScalingFactor(this, a4, (unsigned int *)v12 + 14);
  if ( DesktopScalingFactor >= 0 )
  {
LABEL_25:
    *((_QWORD *)v12 + 145) = 0;
    v16 = (_QWORD *)*((_QWORD *)this + 15);
    *(_QWORD *)v12 = (char *)this + 112;
    *((_QWORD *)v12 + 1) = v16;
    *v16 = v12;
    ++*((_DWORD *)this + 26);
    *((_QWORD *)this + 15) = v12;
    return (unsigned int)DesktopScalingFactor;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v15 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      69,
      (unsigned int)&WPP_7fbfedf3cb2c3dda177afd18a098990f_Traceguids,
      v15,
      (__int64)"GetDesktopScalingFactor failed",
      DesktopScalingFactor);
  }
  return (unsigned int)DesktopScalingFactor;
}

```

## disassembly

```asm
0x1400333cc  mov     [rsp+arg_8], rbx
0x1400333d1  push    rbp
0x1400333d2  push    rsi
0x1400333d3  push    rdi
0x1400333d4  push    r14
0x1400333d6  push    r15
0x1400333d8  sub     rsp, 140h
0x1400333df  mov     rax, cs:__security_cookie
0x1400333e6  xor     rax, rsp
0x1400333e9  mov     [rsp+168h+var_38], rax
0x1400333f1  mov     r14, [rsp+168h+lprcSrc]
0x1400333f9  mov     r15, rdx
0x1400333fc  mov     rdx, r9; HWND
0x1400333ff  mov     rdi, r9
0x140033402  mov     esi, r8d
0x140033405  mov     rbp, rcx
0x140033408  call    ?HasHintsForWindow@CRdpHintManager@@EEAAHPEAUHWND__@@@Z; CRdpHintManager::HasHintsForWindow(HWND__ *)
0x14003340d  test    eax, eax
0x14003340f  jz      short loc_140033466
0x140033411  mov     rax, cs:WPP_GLOBAL_Control
0x140033418  lea     rsi, WPP_GLOBAL_Control
0x14003341f  cmp     rax, rsi
0x140033422  jz      short loc_14003345C
0x140033424  test    dword ptr [rax+1Ch], 200h
0x14003342b  jz      short loc_14003345C
0x14003342d  cmp     byte ptr [rax+19h], 2
0x140033431  jb      short loc_14003345C
0x140033433  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140033438  mov     rcx, cs:WPP_GLOBAL_Control
0x14003343f  lea     r8, WPP_7fbfedf3cb2c3dda177afd18a098990f_Traceguids
0x140033446  mov     edx, 42h ; 'B'
0x14003344b  mov     [rsp+168h+var_148], rdi
0x140033450  mov     r9d, eax
0x140033453  mov     rcx, [rcx+10h]
0x140033457  call    WPP_SF_Dq
0x14003345c  mov     edi, 800700B7h
0x140033461  jmp     loc_14003361E
0x140033466  mov     ecx, 908h; cb
0x14003346b  call    cs:__imp_CoTaskMemAlloc
0x140033471  mov     rbx, rax
0x140033474  test    rax, rax
0x140033477  jnz     short loc_1400334D0
0x140033479  mov     rax, cs:WPP_GLOBAL_Control
0x140033480  lea     rsi, WPP_GLOBAL_Control
0x140033487  cmp     rax, rsi
0x14003348a  jz      short loc_1400334C6
0x14003348c  test    byte ptr [rax+1Ch], 8
0x140033490  jz      short loc_1400334C6
0x140033492  cmp     byte ptr [rax+19h], 2
0x140033496  jb      short loc_1400334C6
0x140033498  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14003349d  lea     rcx, aCotaskmemalloc_2; "\"CoTaskMemAlloc( TSMM_VIDEO_HINT_NODE "...
0x1400334a4  mov     r9d, eax
0x1400334a7  mov     [rsp+168h+var_148], rcx
0x1400334ac  lea     edx, [rbx+43h]
0x1400334af  mov     rcx, cs:WPP_GLOBAL_Control
0x1400334b6  lea     r8, WPP_7fbfedf3cb2c3dda177afd18a098990f_Traceguids
0x1400334bd  mov     rcx, [rcx+10h]
0x1400334c1  call    WPP_SF_Ds
0x1400334c6  mov     edi, 8007000Eh
0x1400334cb  jmp     loc_14003361E
0x1400334d0  xor     edx, edx; Val
0x1400334d2  mov     r8d, 908h; Size
0x1400334d8  mov     rcx, rbx; void *
0x1400334db  call    memset_0
0x1400334e0  xor     edx, edx; Val
0x1400334e2  mov     [rbx+10h], r15
0x1400334e6  mov     r8d, 100h; Size
0x1400334ec  mov     [rbx+18h], esi
0x1400334ef  lea     rcx, [rsp+168h+ClassName]; void *
0x1400334f4  mov     [rbx+20h], rdi
0x1400334f8  call    memset_0
0x1400334fd  mov     r8d, 80h; nMaxCount
0x140033503  lea     rdx, [rsp+168h+ClassName]; lpClassName
0x140033508  mov     rcx, rdi; hWnd
0x14003350b  call    cs:__imp_GetClassNameW
0x140033511  lea     rsi, WPP_GLOBAL_Control
0x140033518  test    eax, eax
0x14003351a  jnz     short loc_14003355B
0x14003351c  mov     rax, cs:WPP_GLOBAL_Control
0x140033523  cmp     rax, rsi
0x140033526  jz      short loc_14003355B
0x140033528  test    dword ptr [rax+1Ch], 200h
0x14003352f  jz      short loc_14003355B
0x140033531  cmp     byte ptr [rax+19h], 3
0x140033535  jb      short loc_14003355B
0x140033537  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14003353c  mov     rcx, cs:WPP_GLOBAL_Control
0x140033543  lea     r8, WPP_7fbfedf3cb2c3dda177afd18a098990f_Traceguids
0x14003354a  mov     edx, 44h ; 'D'
0x14003354f  mov     r9d, eax
0x140033552  mov     rcx, [rcx+10h]
0x140033556  call    WPP_SF_d
0x14003355b  lea     rdx, aVirtualmmrvide; "VirtualMMRVideoWindowClass"
0x140033562  lea     rcx, [rsp+168h+ClassName]; String1
0x140033567  call    wcscmp_0
0x14003356c  xor     ecx, ecx
0x14003356e  test    eax, eax
0x140033570  setz    cl
0x140033573  mov     [rbx+490h], ecx
0x140033579  test    r14, r14
0x14003357c  jnz     short loc_1400335E4
0x14003357e  lea     r8, [rbx+38h]; unsigned int *
0x140033582  mov     [rbx+3Ch], r14d
0x140033586  mov     rdx, rdi; HWND
0x140033589  mov     rcx, rbp; this
0x14003358c  call    ?GetDesktopScalingFactor@CRdpHintManager@@AEAAJPEAUHWND__@@PEAK@Z; CRdpHintManager::GetDesktopScalingFactor(HWND__ *,ulong *)
0x140033591  mov     edi, eax
0x140033593  test    eax, eax
0x140033595  jns     short loc_1400335FA
0x140033597  mov     rax, cs:WPP_GLOBAL_Control
0x14003359e  cmp     rax, rsi
0x1400335a1  jz      short loc_14003361E
0x1400335a3  test    byte ptr [rax+1Ch], 8
0x1400335a7  jz      short loc_14003361E
0x1400335a9  cmp     byte ptr [rax+19h], 2
0x1400335ad  jb      short loc_14003361E
0x1400335af  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400335b4  lea     rcx, aGetdesktopscal; "GetDesktopScalingFactor failed"
0x1400335bb  mov     [rsp+168h+var_140], edi
0x1400335bf  mov     [rsp+168h+var_148], rcx
0x1400335c4  lea     edx, [r14+45h]
0x1400335c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400335cf  lea     r8, WPP_7fbfedf3cb2c3dda177afd18a098990f_Traceguids
0x1400335d6  mov     r9d, eax
0x1400335d9  mov     rcx, [rcx+10h]
0x1400335dd  call    WPP_SF_DsD
0x1400335e2  jmp     short loc_14003361E
0x1400335e4  xor     edi, edi
0x1400335e6  mov     dword ptr [rbx+3Ch], 1
0x1400335ed  lea     rcx, [rbx+28h]; lprcDst
0x1400335f1  mov     rdx, r14; lprcSrc
0x1400335f4  call    cs:__imp_CopyRect
0x1400335fa  mov     qword ptr [rbx+488h], 0
0x140033605  lea     rcx, [rbp+70h]
0x140033609  mov     rax, [rcx+8]
0x14003360d  mov     [rbx], rcx
0x140033610  mov     [rbx+8], rax
0x140033614  mov     [rax], rbx
0x140033617  inc     dword ptr [rbp+68h]
0x14003361a  mov     [rcx+8], rbx
0x14003361e  mov     eax, edi
0x140033620  mov     rcx, [rsp+168h+var_38]
0x140033628  xor     rcx, rsp; StackCookie
0x14003362b  call    __security_check_cookie
0x140033630  mov     rbx, [rsp+168h+arg_8]
0x140033638  add     rsp, 140h
0x14003363f  pop     r15
0x140033641  pop     r14
0x140033643  pop     rdi
0x140033644  pop     rsi
0x140033645  pop     rbp
0x140033646  retn
```
