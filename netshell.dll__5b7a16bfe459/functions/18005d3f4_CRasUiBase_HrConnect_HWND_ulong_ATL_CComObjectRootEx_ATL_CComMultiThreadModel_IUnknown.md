# CRasUiBase::HrConnect(HWND__ *,ulong,ATL::CComObjectRootEx<ATL::CComMultiThreadModel> *,IUnknown *)

- ea: `0x18005d3f4`
- end: `0x18005d556`
- name: `?HrConnect@CRasUiBase@@IEAAJPEAUHWND__@@KPEAV?$CComObjectRootEx@VCComMultiThreadModel@ATL@@@ATL@@PEAUIUnknown@@@Z`
- size: `354`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18005d900`

## callees

- `0x180009140`
- `0x18001e1e0`
- `0x18005d3f4`
- `0x180061aa4`
- `0x180061d50`
- `0x180061db0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18005d4ba`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18005d4ba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005d4c8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005d4c8`
- `RASDLG!RasDialDlgW` at `0x18005d4f9`
- `RASDLG!RasDialDlgW` at `0x18005d4f9`

## pseudocode

```c
__int64 __fastcall CRasUiBase::HrConnect(struct INetConnection **a1, HWND a2)
{
  struct INetConnection *v2; // rcx
  DWORD RasConnectionInfo; // ebx
  unsigned int *v5; // r9
  int EntryProperties; // eax
  void *v7; // rdi
  int v8; // eax
  HANDLE Thread; // rax
  DWORD ThreadId[2]; // [rsp+30h] [rbp-21h] BYREF
  struct tagRASDIALDLG Info; // [rsp+38h] [rbp-19h] BYREF
  LPWSTR lpszPhonebook[2]; // [rsp+68h] [rbp+17h] BYREF
  __int128 v14; // [rsp+78h] [rbp+27h]

  v2 = *a1;
  if ( v2 )
  {
    *(_OWORD *)lpszPhonebook = 0;
    v14 = 0;
    RasConnectionInfo = HrRciGetRasConnectionInfo(v2, (struct tagRASCON_INFO *)lpszPhonebook);
    if ( !RasConnectionInfo )
    {
      *(_QWORD *)ThreadId = 0;
      EntryProperties = HrRasGetEntryProperties(
                          lpszPhonebook[0],
                          lpszPhonebook[1],
                          (struct tagRASENTRYW **)ThreadId,
                          v5);
      v7 = *(void **)ThreadId;
      RasConnectionInfo = EntryProperties;
      if ( EntryProperties >= 0
        && *(_QWORD *)ThreadId
        && ((v8 = *(_DWORD *)(*(_QWORD *)ThreadId + 3496LL), v8 == 2) || v8 == 5)
        && !*(_WORD *)(*(_QWORD *)ThreadId + 3524LL)
        && !*(_WORD *)(*(_QWORD *)ThreadId + 5092LL) )
      {
        ThreadId[0] = 0;
        Thread = CreateThread(0, 0, CRasUiBase::LaunchVANThreadProc, 0, 0, ThreadId);
        if ( Thread )
          CloseHandle(Thread);
      }
      else
      {
        memset(&Info.dwFlags, 0, 36);
        Info.dwSize = 48;
        Info.hwndOwner = a2;
        if ( !RasDialDlgW(lpszPhonebook[0], lpszPhonebook[1], 0, &Info) )
        {
          RasConnectionInfo = Info.dwError;
          if ( Info.dwError )
          {
            if ( (int)Info.dwError > 0 )
              RasConnectionInfo = LOWORD(Info.dwError) | 0x80070000;
          }
          else
          {
            RasConnectionInfo = 1;
          }
        }
      }
      RciFree((LPVOID *)lpszPhonebook);
      if ( v7 )
        MemFree(v7);
    }
  }
  else
  {
    return (DWORD)-2147418113;
  }
  return RasConnectionInfo;
}

```

## disassembly

```asm
0x18005d3f4  mov     [rsp-8+arg_10], rbx
0x18005d3f9  mov     [rsp-8+arg_18], rsi
0x18005d3fe  push    rbp
0x18005d3ff  push    rdi
0x18005d400  push    r14
0x18005d402  lea     rbp, [rsp-3Fh]
0x18005d407  sub     rsp, 90h
0x18005d40e  mov     rax, cs:__security_cookie
0x18005d415  xor     rax, rsp
0x18005d418  mov     [rbp+4Fh+var_18], rax
0x18005d41c  mov     rcx, [rcx]; struct INetConnection *
0x18005d41f  xor     r14d, r14d
0x18005d422  mov     rsi, rdx
0x18005d425  test    rcx, rcx
0x18005d428  jnz     short loc_18005D434
0x18005d42a  mov     ebx, 8000FFFFh
0x18005d42f  jmp     loc_18005D530
0x18005d434  xorps   xmm0, xmm0
0x18005d437  lea     rdx, [rbp+4Fh+lpszPhonebook]; struct tagRASCON_INFO *
0x18005d43b  movups  xmmword ptr [rbp+4Fh+lpszPhonebook], xmm0
0x18005d43f  movups  [rbp+4Fh+var_28], xmm0
0x18005d443  call    ?HrRciGetRasConnectionInfo@@YAJPEAUINetConnection@@PEAUtagRASCON_INFO@@@Z; HrRciGetRasConnectionInfo(INetConnection *,tagRASCON_INFO *)
0x18005d448  mov     ebx, eax
0x18005d44a  test    eax, eax
0x18005d44c  jnz     loc_18005D530
0x18005d452  mov     rdx, [rbp+4Fh+lpszPhonebook+8]; LPCWSTR
0x18005d456  lea     r8, [rbp+4Fh+ThreadId]; struct tagRASENTRYW **
0x18005d45a  mov     rcx, [rbp+4Fh+lpszPhonebook]; LPCWSTR
0x18005d45e  mov     qword ptr [rbp+4Fh+ThreadId], r14
0x18005d462  call    ?HrRasGetEntryProperties@@YAJPEBG0PEAPEAUtagRASENTRYW@@PEAK@Z; HrRasGetEntryProperties(ushort const *,ushort const *,tagRASENTRYW * *,ulong *)
0x18005d467  mov     rdi, qword ptr [rbp+4Fh+ThreadId]
0x18005d46b  mov     ebx, eax
0x18005d46d  test    eax, eax
0x18005d46f  js      short loc_18005D4D0
0x18005d471  test    rdi, rdi
0x18005d474  jz      short loc_18005D4D0
0x18005d476  mov     eax, [rdi+0DA8h]
0x18005d47c  cmp     eax, 2
0x18005d47f  jz      short loc_18005D486
0x18005d481  cmp     eax, 5
0x18005d484  jnz     short loc_18005D4D0
0x18005d486  cmp     [rdi+0DC4h], r14w
0x18005d48e  jnz     short loc_18005D4D0
0x18005d490  cmp     [rdi+13E4h], r14w
0x18005d498  jnz     short loc_18005D4D0
0x18005d49a  lea     rax, [rbp+4Fh+ThreadId]
0x18005d49e  mov     [rbp+4Fh+ThreadId], r14d
0x18005d4a2  mov     [rsp+0A0h+lpThreadId], rax; lpThreadId
0x18005d4a7  lea     r8, ?LaunchVANThreadProc@CRasUiBase@@KAP6AKPEAX@ZXZ; lpStartAddress
0x18005d4ae  xor     r9d, r9d; lpParameter
0x18005d4b1  mov     [rsp+0A0h+dwCreationFlags], r14d; dwCreationFlags
0x18005d4b6  xor     edx, edx; dwStackSize
0x18005d4b8  xor     ecx, ecx; lpThreadAttributes
0x18005d4ba  call    cs:__imp_CreateThread
0x18005d4c0  test    rax, rax
0x18005d4c3  jz      short loc_18005D51A
0x18005d4c5  mov     rcx, rax; hObject
0x18005d4c8  call    cs:__imp_CloseHandle
0x18005d4ce  jmp     short loc_18005D51A
0x18005d4d0  mov     rdx, [rbp+4Fh+lpszPhonebook+8]; lpszEntry
0x18005d4d4  lea     r9, [rbp+4Fh+Info]; lpInfo
0x18005d4d8  mov     rcx, [rbp+4Fh+lpszPhonebook]; lpszPhonebook
0x18005d4dc  xorps   xmm0, xmm0
0x18005d4df  movups  xmmword ptr [rbp+4Fh+Info.dwSize], xmm0
0x18005d4e3  xor     r8d, r8d; lpszPhoneNumber
0x18005d4e6  mov     [rbp+4Fh+Info.dwSize], 30h ; '0'
0x18005d4ed  mov     [rbp+4Fh+Info.hwndOwner], rsi
0x18005d4f1  movups  xmmword ptr [rbp+4Fh+Info.xDlg], xmm0
0x18005d4f5  movups  xmmword ptr [rbp+4Fh+Info.reserved], xmm0
0x18005d4f9  call    cs:__imp_RasDialDlgW
0x18005d4ff  test    eax, eax
0x18005d501  jnz     short loc_18005D51A
0x18005d503  mov     ebx, [rbp+4Fh+Info.dwError]
0x18005d506  test    ebx, ebx
0x18005d508  jnz     short loc_18005D50F
0x18005d50a  lea     ebx, [rax+1]
0x18005d50d  jmp     short loc_18005D51A
0x18005d50f  jle     short loc_18005D51A
0x18005d511  movzx   ebx, bx
0x18005d514  or      ebx, 80070000h
0x18005d51a  lea     rcx, [rbp+4Fh+lpszPhonebook]; struct tagRASCON_INFO *
0x18005d51e  call    ?RciFree@@YAXPEAUtagRASCON_INFO@@@Z; RciFree(tagRASCON_INFO *)
0x18005d523  test    rdi, rdi
0x18005d526  jz      short loc_18005D530
0x18005d528  mov     rcx, rdi; lpMem
0x18005d52b  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x18005d530  mov     eax, ebx
0x18005d532  mov     rcx, [rbp+4Fh+var_18]
0x18005d536  xor     rcx, rsp; StackCookie
0x18005d539  call    __security_check_cookie
0x18005d53e  lea     r11, [rsp+0A0h+var_10]
0x18005d546  mov     rbx, [r11+30h]
0x18005d54a  mov     rsi, [r11+38h]
0x18005d54e  mov     rsp, r11
0x18005d551  pop     r14
0x18005d553  pop     rdi
0x18005d554  pop     rbp
0x18005d555  retn
```
