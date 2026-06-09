# CRdrFileTransfer::CopyHdropToTempPath(_DROPFILES *,unsigned __int64)

- ea: `0x140046784`
- end: `0x140046a78`
- name: `?CopyHdropToTempPath@CRdrFileTransfer@@QEAAJPEAU_DROPFILES@@_K@Z`
- size: `756`
- prototype: `__int64 __fastcall(CRdrFileTransfer *this, const CHAR *, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x140062de0`

## callees

- `0x140004b1c`
- `0x1400056c4`
- `0x140005750`
- `0x14000c750`
- `0x140011054`
- `0x1400186e4`
- `0x140046784`
- `0x140046a80`
- `0x140046bd0`
- `0x14006b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400469e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400469e3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140046a63`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140046a63`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1400469d5`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1400469d5`

## string_xrefs

- `0x1400468e5`: `CreateTempPath failed!`
- `0x140046a2d`: `CopyToTempPath failed!`

## pseudocode

```c
__int64 __fastcall CRdrFileTransfer::CopyHdropToTempPath(CRdrFileTransfer *this, const CHAR *a2, __int64 a3)
{
  signed int TempPath; // ebx
  CHAR *v7; // rsi
  BOOL *v8; // rbp
  unsigned int CurrentThreadActivityIdPrefix; // eax
  unsigned int v10; // eax
  unsigned int v11; // eax
  int v12; // edx
  const char *v13; // rcx
  unsigned int v14; // eax
  WCHAR *lpWideCharStr; // rax
  unsigned int v16; // eax
  signed int LastError; // eax

  if ( !*((_DWORD *)this + 12) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_aff8ace9ce173a6be6d945882be5b339_Traceguids);
    }
    return (unsigned int)-2147418113;
  }
  v7 = 0;
  if ( *((_DWORD *)this + 274) )
    goto LABEL_45;
  v8 = (BOOL *)(a2 + 16);
  if ( *((_DWORD *)a2 + 4) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        15,
        WPP_aff8ace9ce173a6be6d945882be5b339_Traceguids,
        CurrentThreadActivityIdPrefix);
    }
    v7 = (CHAR *)&a2[*(unsigned int *)a2];
    goto LABEL_14;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    v14 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_aff8ace9ce173a6be6d945882be5b339_Traceguids, v14);
  }
  lpWideCharStr = (WCHAR *)PAL_System_MemAlloc(2 * a3 - 40);
  v7 = (CHAR *)lpWideCharStr;
  if ( lpWideCharStr )
  {
    if ( !MultiByteToWideChar(0, 0, &a2[*(unsigned int *)a2], a3 - 20, lpWideCharStr, a3 - 20) )
    {
      LastError = GetLastError();
      TempPath = LastError;
      if ( LastError > 0 )
        TempPath = (unsigned __int16)LastError | 0x80070000;
LABEL_47:
      if ( !*v8 )
        LocalFree(v7);
      return (unsigned int)TempPath;
    }
LABEL_14:
    if ( (*(unsigned int (__fastcall **)(CRdrFileTransfer *, CHAR *))(*(_QWORD *)this + 48LL))(this, v7) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        v10 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_aff8ace9ce173a6be6d945882be5b339_Traceguids, v10);
      }
      if ( !*((_DWORD *)this + 273) )
      {
        TempPath = CRdrFileTransfer::CreateTempPath(this);
        if ( TempPath < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v11 = RdpWppGetCurrentThreadActivityIdPrefix();
            v12 = 19;
            v13 = "CreateTempPath failed!";
LABEL_25:
            WPP_SF_DsD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v12,
              (unsigned int)WPP_aff8ace9ce173a6be6d945882be5b339_Traceguids,
              v11,
              (__int64)v13,
              TempPath);
            goto LABEL_46;
          }
          goto LABEL_46;
        }
      }
      TempPath = CRdrFileTransfer::CopyToTempPath(this, (const unsigned __int16 *)v7);
      if ( TempPath < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v11 = RdpWppGetCurrentThreadActivityIdPrefix();
          v12 = 20;
          v13 = "CopyToTempPath failed!";
          goto LABEL_25;
        }
LABEL_46:
        if ( !v7 )
          return (unsigned int)TempPath;
        goto LABEL_47;
      }
      *((_DWORD *)this + 274) = 1;
      *((_DWORD *)this + 273) = 1;
    }
LABEL_45:
    TempPath = 0;
    v8 = (BOOL *)(a2 + 16);
    goto LABEL_46;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v16 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Ds(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      17,
      (unsigned int)WPP_aff8ace9ce173a6be6d945882be5b339_Traceguids,
      v16,
      (__int64)"WCHAR[]");
  }
  return (unsigned int)-2147024882;
}

```

## disassembly

```asm
0x140046784  push    rbx
0x140046786  push    rbp
0x140046787  push    rsi
0x140046788  push    rdi
0x140046789  push    r13
0x14004678b  push    r14
0x14004678d  sub     rsp, 38h
0x140046791  cmp     dword ptr [rcx+30h], 0
0x140046795  mov     rbx, r8
0x140046798  mov     r13, rdx
0x14004679b  mov     r14, rcx
0x14004679e  jnz     short loc_1400467DE
0x1400467a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400467a7  lea     rdi, WPP_GLOBAL_Control
0x1400467ae  cmp     rcx, rdi
0x1400467b1  jz      short loc_1400467D4
0x1400467b3  test    byte ptr [rcx+1Ch], 1
0x1400467b7  jz      short loc_1400467D4
0x1400467b9  cmp     byte ptr [rcx+19h], 1
0x1400467bd  jb      short loc_1400467D4
0x1400467bf  mov     rcx, [rcx+10h]
0x1400467c3  lea     r8, WPP_aff8ace9ce173a6be6d945882be5b339_Traceguids
0x1400467ca  mov     edx, 0Eh
0x1400467cf  call    WPP_SF_
0x1400467d4  mov     ebx, 8000FFFFh
0x1400467d9  jmp     loc_140046A69
0x1400467de  xor     esi, esi
0x1400467e0  cmp     [rcx+448h], esi
0x1400467e6  jnz     loc_140046A4F
0x1400467ec  lea     rbp, [rdx+10h]
0x1400467f0  cmp     [rbp+0], esi
0x1400467f3  jz      loc_140046914
0x1400467f9  mov     rax, cs:WPP_GLOBAL_Control
0x140046800  lea     rdi, WPP_GLOBAL_Control
0x140046807  cmp     rax, rdi
0x14004680a  jz      short loc_14004683A
0x14004680c  test    byte ptr [rax+1Ch], 1
0x140046810  jz      short loc_14004683A
0x140046812  cmp     byte ptr [rax+19h], 5
0x140046816  jb      short loc_14004683A
0x140046818  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14004681d  mov     rcx, cs:WPP_GLOBAL_Control
0x140046824  lea     edx, [rsi+0Fh]
0x140046827  mov     r9d, eax
0x14004682a  lea     r8, WPP_aff8ace9ce173a6be6d945882be5b339_Traceguids
0x140046831  mov     rcx, [rcx+10h]
0x140046835  call    WPP_SF_d
0x14004683a  mov     esi, [r13+0]
0x14004683e  add     rsi, r13
0x140046841  mov     rax, [r14]
0x140046844  mov     rdx, rsi
0x140046847  mov     rcx, r14
0x14004684a  mov     rax, [rax+30h]
0x14004684e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140046853  test    eax, eax
0x140046855  jz      loc_140046A4F
0x14004685b  mov     rax, cs:WPP_GLOBAL_Control
0x140046862  cmp     rax, rdi
0x140046865  jz      short loc_140046897
0x140046867  test    byte ptr [rax+1Ch], 1
0x14004686b  jz      short loc_140046897
0x14004686d  cmp     byte ptr [rax+19h], 5
0x140046871  jb      short loc_140046897
0x140046873  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140046878  mov     rcx, cs:WPP_GLOBAL_Control
0x14004687f  lea     r8, WPP_aff8ace9ce173a6be6d945882be5b339_Traceguids
0x140046886  mov     edx, 12h
0x14004688b  mov     r9d, eax
0x14004688e  mov     rcx, [rcx+10h]
0x140046892  call    WPP_SF_d
0x140046897  cmp     dword ptr [r14+444h], 0
0x14004689f  jnz     loc_1400469FA
0x1400468a5  mov     rcx, r14; this
0x1400468a8  call    ?CreateTempPath@CRdrFileTransfer@@IEAAJXZ; CRdrFileTransfer::CreateTempPath(void)
0x1400468ad  mov     ebx, eax
0x1400468af  test    eax, eax
0x1400468b1  jns     loc_1400469FA
0x1400468b7  mov     rax, cs:WPP_GLOBAL_Control
0x1400468be  cmp     rax, rdi
0x1400468c1  jz      loc_140046A55
0x1400468c7  test    byte ptr [rax+1Ch], 8
0x1400468cb  jz      loc_140046A55
0x1400468d1  cmp     byte ptr [rax+19h], 2
0x1400468d5  jb      loc_140046A55
0x1400468db  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400468e0  mov     edx, 13h
0x1400468e5  lea     rcx, aCreatetemppath; "CreateTempPath failed!"
0x1400468ec  mov     [rsp+68h+cchWideChar], ebx
0x1400468f0  lea     r8, WPP_aff8ace9ce173a6be6d945882be5b339_Traceguids
0x1400468f7  mov     [rsp+68h+lpWideCharStr], rcx
0x1400468fc  mov     r9d, eax
0x1400468ff  mov     rcx, cs:WPP_GLOBAL_Control
0x140046906  mov     rcx, [rcx+10h]
0x14004690a  call    WPP_SF_DsD
0x14004690f  jmp     loc_140046A55
0x140046914  mov     rax, cs:WPP_GLOBAL_Control
0x14004691b  lea     rdi, WPP_GLOBAL_Control
0x140046922  cmp     rax, rdi
0x140046925  jz      short loc_140046957
0x140046927  test    byte ptr [rax+1Ch], 1
0x14004692b  jz      short loc_140046957
0x14004692d  cmp     byte ptr [rax+19h], 5
0x140046931  jb      short loc_140046957
0x140046933  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140046938  mov     rcx, cs:WPP_GLOBAL_Control
0x14004693f  lea     r8, WPP_aff8ace9ce173a6be6d945882be5b339_Traceguids
0x140046946  mov     edx, 10h
0x14004694b  mov     r9d, eax
0x14004694e  mov     rcx, [rcx+10h]
0x140046952  call    WPP_SF_d
0x140046957  lea     rcx, ds:0FFFFFFFFFFFFFFD8h[rbx*2]
0x14004695f  call    PAL_System_MemAlloc
0x140046964  mov     rsi, rax
0x140046967  test    rax, rax
0x14004696a  jnz     short loc_1400469BC
0x14004696c  mov     rax, cs:WPP_GLOBAL_Control
0x140046973  cmp     rax, rdi
0x140046976  jz      short loc_1400469B2
0x140046978  test    byte ptr [rax+1Ch], 8
0x14004697c  jz      short loc_1400469B2
0x14004697e  cmp     byte ptr [rax+19h], 2
0x140046982  jb      short loc_1400469B2
0x140046984  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140046989  lea     rcx, aWchar; "WCHAR[]"
0x140046990  mov     r9d, eax
0x140046993  mov     [rsp+68h+lpWideCharStr], rcx
0x140046998  lea     edx, [rsi+11h]
0x14004699b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400469a2  lea     r8, WPP_aff8ace9ce173a6be6d945882be5b339_Traceguids
0x1400469a9  mov     rcx, [rcx+10h]
0x1400469ad  call    WPP_SF_Ds
0x1400469b2  mov     ebx, 8007000Eh
0x1400469b7  jmp     loc_140046A69
0x1400469bc  mov     r8d, [r13+0]
0x1400469c0  lea     r9d, [rbx-14h]; cbMultiByte
0x1400469c4  mov     [rsp+68h+cchWideChar], r9d; cchWideChar
0x1400469c9  add     r8, r13; lpMultiByteStr
0x1400469cc  xor     edx, edx; dwFlags
0x1400469ce  mov     [rsp+68h+lpWideCharStr], rax; lpWideCharStr
0x1400469d3  xor     ecx, ecx; CodePage
0x1400469d5  call    cs:__imp_MultiByteToWideChar
0x1400469db  test    eax, eax
0x1400469dd  jnz     loc_140046841
0x1400469e3  call    cs:__imp_GetLastError
0x1400469e9  mov     ebx, eax
0x1400469eb  test    eax, eax
0x1400469ed  jle     short loc_140046A5A
0x1400469ef  movzx   ebx, ax
0x1400469f2  or      ebx, 80070000h
0x1400469f8  jmp     short loc_140046A5A
0x1400469fa  mov     rdx, rsi; unsigned __int16 *
0x1400469fd  mov     rcx, r14; this
0x140046a00  call    ?CopyToTempPath@CRdrFileTransfer@@IEAAJPEBG@Z; CRdrFileTransfer::CopyToTempPath(ushort const *)
0x140046a05  mov     ebx, eax
0x140046a07  test    eax, eax
0x140046a09  jns     short loc_140046A39
0x140046a0b  mov     rax, cs:WPP_GLOBAL_Control
0x140046a12  cmp     rax, rdi
0x140046a15  jz      short loc_140046A55
0x140046a17  test    byte ptr [rax+1Ch], 8
0x140046a1b  jz      short loc_140046A55
0x140046a1d  cmp     byte ptr [rax+19h], 2
0x140046a21  jb      short loc_140046A55
0x140046a23  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140046a28  mov     edx, 14h
0x140046a2d  lea     rcx, aCopytotemppath; "CopyToTempPath failed!"
0x140046a34  jmp     loc_1400468EC
0x140046a39  mov     dword ptr [r14+448h], 1
0x140046a44  mov     dword ptr [r14+444h], 1
0x140046a4f  xor     ebx, ebx
0x140046a51  lea     rbp, [r13+10h]
0x140046a55  test    rsi, rsi
0x140046a58  jz      short loc_140046A69
0x140046a5a  cmp     dword ptr [rbp+0], 0
0x140046a5e  jnz     short loc_140046A69
0x140046a60  mov     rcx, rsi; hMem
0x140046a63  call    cs:__imp_LocalFree
0x140046a69  mov     eax, ebx
0x140046a6b  add     rsp, 38h
0x140046a6f  pop     r14
0x140046a71  pop     r13
0x140046a73  pop     rdi
0x140046a74  pop     rsi
0x140046a75  pop     rbp
0x140046a76  pop     rbx
0x140046a77  retn
```
