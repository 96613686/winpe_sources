# LipsAuditReportCrimsonSecurityEvent

- ea: `0x180008744`
- end: `0x180008a8f`
- name: `LipsAuditReportCrimsonSecurityEvent`
- size: `843`
- prototype: `__int64 __fastcall(int, int, __int64 *, unsigned int)`
- caller_count: `4`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180003de0`
- `0x180007160`
- `0x1800072e0`
- `0x1800080e0`

## callees

- `0x180006f00`
- `0x180006f60`
- `0x180008744`
- `0x18000c4d0`
- `0x18000e510`
- `0x18000f660`
- `0x180042ef8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000892f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800089ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800089e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008a41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000892f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800089ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800089e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008a41`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008a5e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008a5e`
- `AUTHZ!AuthziInitializeAuditParams` at `0x180008925`
- `AUTHZ!AuthziInitializeAuditParams` at `0x180008925`
- `AUTHZ!AuthziInitializeAuditEvent` at `0x1800089a4`
- `AUTHZ!AuthziInitializeAuditEvent` at `0x1800089a4`
- `AUTHZ!AuthzFreeAuditEvent` at `0x180008a21`
- `AUTHZ!AuthzFreeAuditEvent` at `0x180008a21`
- `AUTHZ!AuthziLogAuditEvent` at `0x1800089dc`
- `AUTHZ!AuthziLogAuditEvent` at `0x1800089dc`

## string_xrefs

- `0x180008a7c`: `LipsAuditReportCrimsonSecurityEvent`

## pseudocode

```c
__int64 __fastcall LipsAuditReportCrimsonSecurityEvent(int a1, int a2, __int64 *a3, unsigned int a4)
{
  __int64 v4; // r10
  __int64 v6; // r13
  __int64 v7; // rdx
  __int64 v8; // r12
  __int64 v9; // r15
  DWORD LastError; // eax
  void *v11; // r11
  unsigned int v12; // edi
  void *v13; // r14
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  LPVOID v16; // rax
  __int64 v17; // r9
  __int64 v18; // rbx
  DWORD v19; // eax
  AUTHZ_AUDIT_EVENT_HANDLE hAuditEvent; // [rsp+60h] [rbp-19h] BYREF
  SIZE_T v21; // [rsp+68h] [rbp-11h] BYREF
  HLOCAL hMem; // [rsp+70h] [rbp-9h] BYREF
  __int128 v23; // [rsp+78h] [rbp-1h] BYREF
  LPVOID v24; // [rsp+88h] [rbp+Fh]

  hMem = 0;
  v24 = 0;
  v23 = 0;
  hAuditEvent = 0;
  v4 = 0;
  v21 = 0;
  while ( dword_180055D08[3 * v4] != a2 )
  {
    if ( (unsigned __int64)++v4 >= 0x18 )
      return 87;
  }
  v6 = (unsigned __int16)v4;
  v7 = (unsigned __int16)word_180055D04[6 * (unsigned __int16)v4];
  if ( (unsigned __int16)v7 > 2u )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_45bd2475f6dc366a4e40f09bda76fd35_Traceguids);
    return 87;
  }
  v8 = 0;
  v9 = 0;
  if ( a3 )
  {
    if ( a4 )
    {
      v8 = *a3;
      if ( a4 > 1 )
      {
        if ( a3[1] )
          v9 = a3[1];
      }
    }
  }
  LastError = NsuSizeTMultiply(32, v7 + 2, &v21);
  v12 = LastError;
  if ( !LastError )
  {
    v16 = IpsecAllocMem(v21);
    v13 = v16;
    if ( v16 )
    {
      v24 = v16;
      if ( (unsigned int)AuthziInitializeAuditParams(
                           a1 != 0,
                           &v23,
                           &hMem,
                           0,
                           word_180055D04[6 * v6],
                           2,
                           v8,
                           2,
                           v9,
                           2,
                           0)
        || (LastError = GetLastError(), (v12 = LastError) == 0) )
      {
        if ( (unsigned int)AuthziInitializeAuditEvent(
                             0,
                             0,
                             gLipsAuditEvents[v6],
                             &v23,
                             0,
                             -1,
                             &qword_18005B2E8,
                             &qword_18005B2E8,
                             &qword_18005B2E8,
                             &qword_18005B2E8,
                             &hAuditEvent)
          || (LastError = GetLastError(), (v12 = LastError) == 0) )
        {
          if ( !(unsigned int)AuthziLogAuditEvent(0, hAuditEvent, 0) )
          {
            LastError = GetLastError();
            v12 = LastError;
            if ( LastError )
            {
              v14 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
              {
                v15 = 17;
                goto LABEL_37;
              }
            }
          }
        }
        else
        {
          v14 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          {
            v15 = 16;
            goto LABEL_37;
          }
        }
      }
      else
      {
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        {
          v15 = 15;
          goto LABEL_37;
        }
      }
    }
    else
    {
      v12 = 8;
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v15 = 14;
        v17 = 8;
LABEL_38:
        WPP_SF_d(v14[2], v15, WPP_45bd2475f6dc366a4e40f09bda76fd35_Traceguids, v17);
      }
    }
    if ( hAuditEvent
      && !AuthzFreeAuditEvent(hAuditEvent)
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v18 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v19 = GetLastError();
      WPP_SF_d(v18, 18, WPP_45bd2475f6dc366a4e40f09bda76fd35_Traceguids, v19);
    }
    goto LABEL_44;
  }
  v13 = v11;
  v14 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    v15 = 13;
LABEL_37:
    v17 = LastError;
    goto LABEL_38;
  }
LABEL_44:
  LocalFree(hMem);
  if ( v13 )
    IpsecFreeMem(v13);
  if ( v12 )
    return LipsReportError(v12, "LipsAuditReportCrimsonSecurityEvent");
  else
    return 0;
}

```

## disassembly

```asm
0x180008744  mov     [rsp-8+arg_0], ecx
0x180008748  push    rbp
0x180008749  push    rbx
0x18000874a  push    rsi
0x18000874b  push    rdi
0x18000874c  push    r12
0x18000874e  push    r13
0x180008750  push    r14
0x180008752  push    r15
0x180008754  lea     rbp, [rsp-1Fh]
0x180008759  sub     rsp, 98h
0x180008760  xor     r11d, r11d
0x180008763  lea     rcx, __ImageBase
0x18000876a  xor     eax, eax
0x18000876c  mov     [rbp+57h+hMem], r11
0x180008770  xorps   xmm0, xmm0
0x180008773  mov     [rbp+57h+var_48], rax
0x180008777  movups  [rbp+57h+var_58], xmm0
0x18000877b  mov     [rbp+57h+hAuditEvent], r11
0x18000877f  mov     r10d, r11d
0x180008782  mov     [rbp+57h+var_68], r11
0x180008786  lea     rax, [r10+r10*2]
0x18000878a  cmp     ds:rva dword_180055D08[rcx+rax*4], edx
0x180008791  jz      short loc_1800087B5
0x180008793  inc     r10
0x180008796  cmp     r10, 18h
0x18000879a  jb      short loc_180008786
0x18000879c  mov     eax, 57h ; 'W'
0x1800087a1  add     rsp, 98h
0x1800087a8  pop     r15
0x1800087aa  pop     r14
0x1800087ac  pop     r13
0x1800087ae  pop     r12
0x1800087b0  pop     rdi
0x1800087b1  pop     rsi
0x1800087b2  pop     rbx
0x1800087b3  pop     rbp
0x1800087b4  retn
0x1800087b5  mov     eax, 0FFFFh
0x1800087ba  cmp     r10w, ax
0x1800087be  jz      short loc_18000879C
0x1800087c0  movzx   r13d, r10w
0x1800087c4  lea     rax, ds:0[r13*2]
0x1800087cc  add     rax, r13
0x1800087cf  movzx   edx, ds:rva word_180055D04[rcx+rax*4]
0x1800087d7  mov     eax, 2
0x1800087dc  cmp     dx, ax
0x1800087df  jbe     short loc_18000881C
0x1800087e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800087e8  lea     rbx, WPP_GLOBAL_Control
0x1800087ef  cmp     rcx, rbx
0x1800087f2  jz      short loc_18000879C
0x1800087f4  test    byte ptr [rcx+1Ch], 10h
0x1800087f8  jz      short loc_18000879C
0x1800087fa  mov     rcx, [rcx+10h]
0x1800087fe  lea     r8, WPP_45bd2475f6dc366a4e40f09bda76fd35_Traceguids
0x180008805  movzx   eax, r10w
0x180008809  mov     r9d, edx
0x18000880c  mov     edx, 0Ch
0x180008811  mov     dword ptr [rsp+0D0h+var_B0], eax
0x180008815  call    WPP_SF_dd
0x18000881a  jmp     short loc_18000879C
0x18000881c  mov     r12, r11
0x18000881f  mov     r15, r11
0x180008822  test    r8, r8
0x180008825  jz      short loc_18000883E
0x180008827  test    r9d, r9d
0x18000882a  jz      short loc_18000883E
0x18000882c  mov     r12, [r8]
0x18000882f  cmp     r9d, 1
0x180008833  jbe     short loc_18000883E
0x180008835  cmp     [r8+8], r11
0x180008839  cmovnz  r15, [r8+8]
0x18000883e  add     rdx, rax
0x180008841  lea     r8, [rbp+57h+var_68]
0x180008845  mov     ecx, 20h ; ' '
0x18000884a  call    NsuSizeTMultiply
0x18000884f  lea     rbx, WPP_GLOBAL_Control
0x180008856  mov     edi, eax
0x180008858  lea     rsi, WPP_45bd2475f6dc366a4e40f09bda76fd35_Traceguids
0x18000885f  test    eax, eax
0x180008861  jz      short loc_18000888A
0x180008863  mov     r14, r11
0x180008866  mov     rcx, cs:WPP_GLOBAL_Control
0x18000886d  cmp     rcx, rbx
0x180008870  jz      loc_180008A5A
0x180008876  test    byte ptr [rcx+1Ch], 10h
0x18000887a  jz      loc_180008A5A
0x180008880  mov     edx, 0Dh
0x180008885  jmp     loc_180008A09
0x18000888a  mov     rcx, [rbp+57h+var_68]
0x18000888e  call    IpsecAllocMem
0x180008893  mov     r14, rax
0x180008896  test    rax, rax
0x180008899  jnz     short loc_1800088C3
0x18000889b  lea     edi, [rax+8]
0x18000889e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800088a5  cmp     rcx, rbx
0x1800088a8  jz      loc_180008A18
0x1800088ae  test    byte ptr [rcx+1Ch], 10h
0x1800088b2  jz      loc_180008A18
0x1800088b8  lea     edx, [rax+0Eh]
0x1800088bb  mov     r9d, edi
0x1800088be  jmp     loc_180008A0C
0x1800088c3  mov     [rsp+0D0h+var_80], 0
0x1800088cc  lea     r8, [rbp+57h+hMem]
0x1800088d0  mov     dword ptr [rsp+0D0h+var_88], 2
0x1800088d8  lea     rdx, [rbp+57h+var_58]
0x1800088dc  mov     [rsp+0D0h+var_90], r15
0x1800088e1  xor     ecx, ecx
0x1800088e3  cmp     [rbp+57h+arg_0], ecx
0x1800088e6  lea     r15, __ImageBase
0x1800088ed  mov     [rbp+57h+var_48], rax
0x1800088f1  lea     rax, ds:0[r13*2]
0x1800088f9  setnz   cl
0x1800088fc  mov     dword ptr [rsp+0D0h+var_98], 2
0x180008904  add     rax, r13
0x180008907  mov     [rsp+0D0h+var_A0], r12
0x18000890c  mov     [rsp+0D0h+var_A8], 2
0x180008914  xor     r9d, r9d
0x180008917  movzx   eax, ds:rva word_180055D04[r15+rax*4]
0x180008920  mov     word ptr [rsp+0D0h+var_B0], ax
0x180008925  call    cs:__imp_AuthziInitializeAuditParams
0x18000892b  test    eax, eax
0x18000892d  jnz     short loc_18000895F
0x18000892f  call    cs:__imp_GetLastError
0x180008935  mov     edi, eax
0x180008937  test    eax, eax
0x180008939  jz      short loc_18000895F
0x18000893b  mov     rcx, cs:WPP_GLOBAL_Control
0x180008942  cmp     rcx, rbx
0x180008945  jz      loc_180008A18
0x18000894b  test    byte ptr [rcx+1Ch], 10h
0x18000894f  jz      loc_180008A18
0x180008955  mov     edx, 0Fh
0x18000895a  jmp     loc_180008A09
0x18000895f  mov     r8, rva gLipsAuditEvents[r15+r13*8]
0x180008967  lea     rax, [rbp+57h+hAuditEvent]
0x18000896b  mov     [rsp+0D0h+var_80], rax
0x180008970  lea     r9, [rbp+57h+var_58]
0x180008974  lea     rax, qword_18005B2E8
0x18000897b  xor     edx, edx
0x18000897d  mov     [rsp+0D0h+var_88], rax
0x180008982  xor     ecx, ecx
0x180008984  mov     [rsp+0D0h+var_90], rax
0x180008989  mov     [rsp+0D0h+var_98], rax
0x18000898e  mov     [rsp+0D0h+var_A0], rax
0x180008993  mov     [rsp+0D0h+var_A8], 0FFFFFFFFh
0x18000899b  mov     [rsp+0D0h+var_B0], 0
0x1800089a4  call    cs:__imp_AuthziInitializeAuditEvent
0x1800089aa  test    eax, eax
0x1800089ac  jnz     short loc_1800089D3
0x1800089ae  call    cs:__imp_GetLastError
0x1800089b4  mov     edi, eax
0x1800089b6  test    eax, eax
0x1800089b8  jz      short loc_1800089D3
0x1800089ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1800089c1  cmp     rcx, rbx
0x1800089c4  jz      short loc_180008A18
0x1800089c6  test    byte ptr [rcx+1Ch], 10h
0x1800089ca  jz      short loc_180008A18
0x1800089cc  mov     edx, 10h
0x1800089d1  jmp     short loc_180008A09
0x1800089d3  mov     rdx, [rbp+57h+hAuditEvent]
0x1800089d7  xor     r8d, r8d
0x1800089da  xor     ecx, ecx
0x1800089dc  call    cs:__imp_AuthziLogAuditEvent
0x1800089e2  test    eax, eax
0x1800089e4  jnz     short loc_180008A18
0x1800089e6  call    cs:__imp_GetLastError
0x1800089ec  mov     edi, eax
0x1800089ee  test    eax, eax
0x1800089f0  jz      short loc_180008A18
0x1800089f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800089f9  cmp     rcx, rbx
0x1800089fc  jz      short loc_180008A18
0x1800089fe  test    byte ptr [rcx+1Ch], 10h
0x180008a02  jz      short loc_180008A18
0x180008a04  mov     edx, 11h
0x180008a09  mov     r9d, eax
0x180008a0c  mov     rcx, [rcx+10h]
0x180008a10  mov     r8, rsi
0x180008a13  call    WPP_SF_d
0x180008a18  mov     rcx, [rbp+57h+hAuditEvent]; hAuditEvent
0x180008a1c  test    rcx, rcx
0x180008a1f  jz      short loc_180008A5A
0x180008a21  call    cs:__imp_AuthzFreeAuditEvent
0x180008a27  test    eax, eax
0x180008a29  jnz     short loc_180008A5A
0x180008a2b  mov     rax, cs:WPP_GLOBAL_Control
0x180008a32  cmp     rax, rbx
0x180008a35  jz      short loc_180008A5A
0x180008a37  test    byte ptr [rax+1Ch], 10h
0x180008a3b  jz      short loc_180008A5A
0x180008a3d  mov     rbx, [rax+10h]
0x180008a41  call    cs:__imp_GetLastError
0x180008a47  mov     edx, 12h
0x180008a4c  mov     r8, rsi
0x180008a4f  mov     r9d, eax
0x180008a52  mov     rcx, rbx
0x180008a55  call    WPP_SF_d
0x180008a5a  mov     rcx, [rbp+57h+hMem]; hMem
0x180008a5e  call    cs:__imp_LocalFree
0x180008a64  test    r14, r14
0x180008a67  jz      short loc_180008A71
0x180008a69  mov     rcx, r14; lpMem
0x180008a6c  call    IpsecFreeMem
0x180008a71  test    edi, edi
0x180008a73  jnz     short loc_180008A7C
0x180008a75  xor     eax, eax
0x180008a77  jmp     loc_1800087A1
0x180008a7c  lea     rdx, aLipsauditrepor; "LipsAuditReportCrimsonSecurityEvent"
0x180008a83  mov     ecx, edi
0x180008a85  call    LipsReportError
0x180008a8a  jmp     loc_1800087A1
```
