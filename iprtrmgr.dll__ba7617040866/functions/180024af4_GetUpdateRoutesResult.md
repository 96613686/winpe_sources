# GetUpdateRoutesResult

- ea: `0x180024af4`
- end: `0x180024d22`
- name: `GetUpdateRoutesResult`
- size: `558`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18003d9b0`

## callees

- `0x180001f30`
- `0x18000ac60`
- `0x180024af4`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x180024bb9`
- `ntdll!RtlAcquireResourceExclusive` at `0x180024bb9`
- `ntdll!RtlReleaseResource` at `0x180024c6a`
- `ntdll!RtlReleaseResource` at `0x180024c6a`
- `KERNEL32!HeapFree` at `0x180024c08`
- `KERNEL32!HeapFree` at `0x180024c08`
- `KERNEL32!LeaveCriticalSection` at `0x180024b61`
- `KERNEL32!LeaveCriticalSection` at `0x180024ca5`
- `KERNEL32!LeaveCriticalSection` at `0x180024cad`
- `KERNEL32!LeaveCriticalSection` at `0x180024b61`
- `KERNEL32!LeaveCriticalSection` at `0x180024ca5`
- `KERNEL32!LeaveCriticalSection` at `0x180024cad`
- `KERNEL32!EnterCriticalSection` at `0x180024b45`
- `KERNEL32!EnterCriticalSection` at `0x180024c96`
- `KERNEL32!EnterCriticalSection` at `0x180024b45`
- `KERNEL32!EnterCriticalSection` at `0x180024c96`

## string_xrefs

- `0x180024b72`: `GetUpdateRoutesResult`
- `0x180024c24`: `GetUpdateRoutesResult : No interface with ICB number %d`
- `0x180024c79`: `Leaving: GetUpdateRoutesResult`

## pseudocode

```c
__int64 __fastcall GetUpdateRoutesResult(unsigned int a1, __int64 a2, _DWORD *a3)
{
  __int64 v5; // rax
  void **v6; // rax
  void ***v7; // r8
  unsigned int v8; // ebx
  void **v9; // rcx
  HANDLE v10; // rcx
  int v12; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v13[2044]; // [rsp+34h] [rbp-CCh] BYREF

  v12 = 0;
  memset_0(v13, 0, sizeof(v13));
  EnterCriticalSection(&RouterStateLock);
  if ( (_DWORD)RouterState )
  {
    LeaveCriticalSection(&RouterStateLock);
    v8 = 900;
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      LOWORD(v12) = 0;
      FormatRRASErrorString(&v12, L"error %d on RM API", 900);
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v12);
    }
  }
  else
  {
    ++HIDWORD(RouterState);
    LeaveCriticalSection(&RouterStateLock);
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      LOWORD(v12) = 0;
      FormatRRASErrorString(&v12, L"Entered: %ws", L"GetUpdateRoutesResult");
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v12);
    }
    RtlAcquireResourceExclusive(&Resource, 1u);
    v5 = InterfaceLookupByICBSeqNumber(a1);
    if ( v5 )
    {
      v6 = (void **)(v5 + 200);
      v7 = (void ***)*v6;
      if ( *v6 == v6 )
      {
        v8 = 1003;
      }
      else
      {
        if ( v7[1] != v6 || (v9 = *v7, (*v7)[1] != v7) )
          __fastfail(3u);
        *v6 = v9;
        v9[1] = v6;
        v10 = IPRouterHeap;
        *a3 = *((_DWORD *)v7 + 4);
        HeapFree(v10, 0, v7);
        v8 = 0;
      }
    }
    else
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        LOWORD(v12) = 0;
        FormatRRASErrorString(&v12, L"GetUpdateRoutesResult : No interface with ICB number %d", a1);
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v12);
      }
      v8 = 1413;
    }
    RtlReleaseResource(&Resource);
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasRtrmgrTraceInfo,
        L"Leaving: GetUpdateRoutesResult");
    EnterCriticalSection(&RouterStateLock);
    --HIDWORD(RouterState);
    LeaveCriticalSection(&RouterStateLock);
  }
  return v8;
}

```

## disassembly

```asm
0x180024af4  mov     [rsp-8+arg_8], rbx
0x180024af9  push    rbp
0x180024afa  push    rdi
0x180024afb  push    r14
0x180024afd  lea     rbp, [rsp-740h]
0x180024b05  sub     rsp, 840h
0x180024b0c  mov     rax, cs:__security_cookie
0x180024b13  xor     rax, rsp
0x180024b16  mov     [rbp+750h+var_20], rax
0x180024b1d  mov     rdi, r8
0x180024b20  mov     rbx, rcx
0x180024b23  xor     eax, eax
0x180024b25  lea     rcx, [rsp+850h+var_81C]; void *
0x180024b2a  mov     r8d, 7FCh; Size
0x180024b30  mov     [rsp+850h+var_820], eax
0x180024b34  xor     edx, edx; Val
0x180024b36  call    memset_0
0x180024b3b  lea     r14, RouterStateLock
0x180024b42  mov     rcx, r14; lpCriticalSection
0x180024b45  call    cs:__imp_EnterCriticalSection
0x180024b4b  cmp     dword ptr cs:RouterState, 0
0x180024b52  mov     rcx, r14; lpCriticalSection
0x180024b55  jnz     loc_180024CAD
0x180024b5b  inc     dword ptr cs:RouterState+4
0x180024b61  call    cs:__imp_LeaveCriticalSection
0x180024b67  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x180024b6e  jge     short loc_180024BB0
0x180024b70  xor     eax, eax
0x180024b72  lea     r8, aGetupdateroute; "GetUpdateRoutesResult"
0x180024b79  lea     rdx, aEnteredWs; "Entered: %ws"
0x180024b80  mov     word ptr [rsp+850h+var_820], ax
0x180024b85  lea     rcx, [rsp+850h+var_820]
0x180024b8a  call    FormatRRASErrorString
0x180024b8f  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x180024b96  jge     short loc_180024BB0
0x180024b98  lea     r8, [rsp+850h+var_820]
0x180024b9d  lea     rdx, RasRtrmgrTraceInfo
0x180024ba4  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180024bab  call    McTemplateU0z_EventWriteTransfer
0x180024bb0  mov     dl, 1; Wait
0x180024bb2  lea     rcx, Resource; Resource
0x180024bb9  call    cs:__imp_RtlAcquireResourceExclusive
0x180024bbf  mov     ecx, ebx
0x180024bc1  call    InterfaceLookupByICBSeqNumber
0x180024bc6  test    rax, rax
0x180024bc9  jz      short loc_180024C19
0x180024bcb  add     rax, 0C8h
0x180024bd1  mov     r8, [rax]; lpMem
0x180024bd4  cmp     r8, rax
0x180024bd7  jnz     short loc_180024BE3
0x180024bd9  mov     ebx, 3EBh
0x180024bde  jmp     loc_180024C63
0x180024be3  cmp     [r8+8], rax
0x180024be7  jnz     short loc_180024C12
0x180024be9  mov     rcx, [r8]
0x180024bec  cmp     [rcx+8], r8
0x180024bf0  jnz     short loc_180024C12
0x180024bf2  mov     [rax], rcx
0x180024bf5  xor     edx, edx; dwFlags
0x180024bf7  mov     [rcx+8], rax
0x180024bfb  mov     eax, [r8+10h]
0x180024bff  mov     rcx, cs:IPRouterHeap; hHeap
0x180024c06  mov     [rdi], eax
0x180024c08  call    cs:__imp_HeapFree
0x180024c0e  xor     ebx, ebx
0x180024c10  jmp     short loc_180024C63
0x180024c12  mov     ecx, 3
0x180024c17  int     29h; Win8: RtlFailFast(ecx)
0x180024c19  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x180024c20  jge     short loc_180024C5E
0x180024c22  xor     eax, eax
0x180024c24  lea     rdx, aGetupdateroute_0; "GetUpdateRoutesResult : No interface wi"...
0x180024c2b  mov     r8d, ebx
0x180024c2e  mov     word ptr [rsp+850h+var_820], ax
0x180024c33  lea     rcx, [rsp+850h+var_820]
0x180024c38  call    FormatRRASErrorString
0x180024c3d  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x180024c44  jge     short loc_180024C5E
0x180024c46  lea     r8, [rsp+850h+var_820]
0x180024c4b  lea     rdx, RasRtrmgrTraceInfo
0x180024c52  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180024c59  call    McTemplateU0z_EventWriteTransfer
0x180024c5e  mov     ebx, 585h
0x180024c63  lea     rcx, Resource; Resource
0x180024c6a  call    cs:__imp_RtlReleaseResource
0x180024c70  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x180024c77  jz      short loc_180024C93
0x180024c79  lea     r8, aLeavingGetupda; "Leaving: GetUpdateRoutesResult"
0x180024c80  lea     rdx, RasRtrmgrTraceInfo
0x180024c87  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180024c8e  call    McTemplateU0z_EventWriteTransfer
0x180024c93  mov     rcx, r14; lpCriticalSection
0x180024c96  call    cs:__imp_EnterCriticalSection
0x180024c9c  dec     dword ptr cs:RouterState+4
0x180024ca2  mov     rcx, r14; lpCriticalSection
0x180024ca5  call    cs:__imp_LeaveCriticalSection
0x180024cab  jmp     short loc_180024CFD
0x180024cad  call    cs:__imp_LeaveCriticalSection
0x180024cb3  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x180024cba  mov     ebx, 384h
0x180024cbf  jge     short loc_180024CFD
0x180024cc1  xor     eax, eax
0x180024cc3  lea     rdx, aErrorDOnRmApi; "error %d on RM API"
0x180024cca  mov     r8d, ebx
0x180024ccd  mov     word ptr [rsp+850h+var_820], ax
0x180024cd2  lea     rcx, [rsp+850h+var_820]
0x180024cd7  call    FormatRRASErrorString
0x180024cdc  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x180024ce3  jge     short loc_180024CFD
0x180024ce5  lea     r8, [rsp+850h+var_820]
0x180024cea  lea     rdx, RasRtrmgrTraceInfo
0x180024cf1  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180024cf8  call    McTemplateU0z_EventWriteTransfer
0x180024cfd  mov     eax, ebx
0x180024cff  mov     rcx, [rbp+750h+var_20]
0x180024d06  xor     rcx, rsp; StackCookie
0x180024d09  call    __security_check_cookie
0x180024d0e  mov     rbx, [rsp+850h+arg_8]
0x180024d16  add     rsp, 840h
0x180024d1d  pop     r14
0x180024d1f  pop     rdi
0x180024d20  pop     rbp
0x180024d21  retn
```
