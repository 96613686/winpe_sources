# ActivateRouterDiscovery

- ea: `0x18004d8d0`
- end: `0x18004dc55`
- name: `ActivateRouterDiscovery`
- size: `901`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180016f34`
- `0x18004fd14`

## callees

- `0x180011790`
- `0x18004d8d0`
- `0x18004deec`
- `0x18004eba4`
- `0x18004f8b8`
- `0x18004ffd8`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `KERNEL32!SetWaitableTimer` at `0x18004db05`
- `KERNEL32!SetWaitableTimer` at `0x18004db05`
- `KERNEL32!GetLastError` at `0x18004db13`
- `KERNEL32!GetLastError` at `0x18004db13`

## string_xrefs

- `0x18004d9e1`: `ActivateRouterDiscovery: Couldnt create sockets for interface %ws. Error %d`
- `0x18004dab0`: `ActivateRouterDiscovery: Couldnt update Icmp Advt. Error %d`

## pseudocode

```c
__int64 __fastcall ActivateRouterDiscovery(const LARGE_INTEGER *a1)
{
  char v2; // al
  __int128 *v3; // r9
  __int128 *v4; // r9
  unsigned int Sockets; // eax
  unsigned int updated; // esi
  char v7; // cl
  LARGE_INTEGER v8; // r8
  __int128 *v9; // r9
  __int128 *v10; // r9
  DWORD LastError; // eax
  __int128 *v13; // r9
  __int128 *v14; // r9
  __int128 v15; // [rsp+38h] [rbp-860h] BYREF
  int v16; // [rsp+48h] [rbp-850h] BYREF
  __int128 v17; // [rsp+4Ch] [rbp-84Ch]
  __int128 v18; // [rsp+5Ch] [rbp-83Ch]
  int v19; // [rsp+6Ch] [rbp-82Ch]
  int v20; // [rsp+70h] [rbp-828h] BYREF
  _BYTE v21[2044]; // [rsp+74h] [rbp-824h] BYREF

  v20 = 0;
  memset_0(v21, 0, sizeof(v21));
  v16 = 0;
  v19 = 0;
  v2 = Microsoft_Windows_RRASEnableBits;
  v17 = 0;
  v18 = 0;
  v15 = 0;
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    v3 = &v15;
    LOWORD(v16) = 0;
    if ( a1 != (const LARGE_INTEGER *)-688LL )
      LODWORD(v3) = (_DWORD)a1 + 688;
    McTemplateU0zjzz_EventWriteTransfer(
      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (unsigned int)RasRtrmgrParamTraceInfo,
      (unsigned int)L"Entered: ActivateRouterDiscovery",
      (_DWORD)v3,
      a1[9].QuadPart,
      (__int64)&v16);
    v2 = Microsoft_Windows_RRASEnableBits;
  }
  if ( a1[21].LowPart < 3 || !a1[27].HighPart )
  {
    if ( v2 < 0 )
    {
      v4 = &v15;
      LOWORD(v16) = 0;
      if ( a1 != (const LARGE_INTEGER *)-688LL )
        LODWORD(v4) = (_DWORD)a1 + 688;
LABEL_41:
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasRtrmgrParamTraceInfo,
        (unsigned int)L"Leaving: ActivateRouterDiscovery",
        (_DWORD)v4,
        a1[9].QuadPart,
        (__int64)&v16);
    }
    return 0;
  }
  Sockets = CreateSockets((__int64)a1);
  updated = Sockets;
  if ( Sockets )
  {
    v7 = Microsoft_Windows_RRASEnableBits;
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      v8 = a1[9];
      LOWORD(v20) = 0;
      LOWORD(v16) = 0;
      FormatRRASErrorString(
        &v20,
        L"ActivateRouterDiscovery: Couldnt create sockets for interface %ws. Error %d",
        v8.QuadPart,
        Sockets);
      goto LABEL_14;
    }
    goto LABEL_18;
  }
  updated = UpdateAdvertisement((__int64)a1);
  if ( updated )
  {
    DeleteSockets(a1);
    v7 = Microsoft_Windows_RRASEnableBits;
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      LOWORD(v20) = 0;
      LOWORD(v16) = 0;
      FormatRRASErrorString(&v20, L"ActivateRouterDiscovery: Couldnt update Icmp Advt. Error %d", updated);
LABEL_14:
      v7 = Microsoft_Windows_RRASEnableBits;
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        v9 = &v15;
        if ( a1 != (const LARGE_INTEGER *)-688LL )
          LODWORD(v9) = (_DWORD)a1 + 688;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasRtrmgrParamTraceInfo,
          (unsigned int)&v20,
          (_DWORD)v9,
          a1[9].QuadPart,
          (__int64)&v16);
        v7 = Microsoft_Windows_RRASEnableBits;
      }
    }
LABEL_18:
    if ( v7 < 0 )
    {
      v10 = &v15;
      LOWORD(v16) = 0;
      if ( a1 != (const LARGE_INTEGER *)-688LL )
        LODWORD(v10) = (_DWORD)a1 + 688;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasRtrmgrParamTraceInfo,
        (unsigned int)L"Leaving: ActivateRouterDiscovery",
        (_DWORD)v10,
        a1[9].QuadPart,
        (__int64)&v16);
    }
    return updated;
  }
  if ( !(unsigned int)SetFiringTimeForAdvt(a1) || SetWaitableTimer(g_hRtrDiscTimer, a1 + 32, 0, 0, 0, 0) )
  {
    a1[28].LowPart = 1;
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      v4 = &v15;
      LOWORD(v16) = 0;
      if ( a1 != (const LARGE_INTEGER *)-688LL )
        LODWORD(v4) = (_DWORD)a1 + 688;
      goto LABEL_41;
    }
    return 0;
  }
  LastError = GetLastError();
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v20) = 0;
    LOWORD(v16) = 0;
    FormatRRASErrorString(&v20, L"ActivateRouterDiscovery: Error %d setting timer", LastError);
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      v13 = &v15;
      if ( a1 != (const LARGE_INTEGER *)-688LL )
        LODWORD(v13) = (_DWORD)a1 + 688;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasRtrmgrParamTraceInfo,
        (unsigned int)&v20,
        (_DWORD)v13,
        a1[9].QuadPart,
        (__int64)&v16);
    }
  }
  DeleteSockets(a1);
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    v14 = &v15;
    LOWORD(v16) = 0;
    if ( a1 != (const LARGE_INTEGER *)-688LL )
      LODWORD(v14) = (_DWORD)a1 + 688;
    McTemplateU0zjzz_EventWriteTransfer(
      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (unsigned int)RasRtrmgrParamTraceInfo,
      (unsigned int)L"Leaving: ActivateRouterDiscovery",
      (_DWORD)v14,
      a1[9].QuadPart,
      (__int64)&v16);
  }
  return 1003;
}

```

## disassembly

```asm
0x18004d8d0  mov     [rsp+arg_8], rbx
0x18004d8d5  mov     [rsp+arg_10], rsi
0x18004d8da  push    rdi
0x18004d8db  push    r12
0x18004d8dd  push    r13
0x18004d8df  sub     rsp, 880h
0x18004d8e6  mov     rax, cs:__security_cookie
0x18004d8ed  xor     rax, rsp
0x18004d8f0  mov     [rsp+898h+var_28], rax
0x18004d8f8  mov     rbx, rcx
0x18004d8fb  xor     eax, eax
0x18004d8fd  lea     rcx, [rsp+898h+var_824]; void *
0x18004d902  mov     [rsp+898h+var_828], eax
0x18004d906  xor     edx, edx; Val
0x18004d908  mov     r8d, 7FCh; Size
0x18004d90e  call    memset_0
0x18004d913  xor     eax, eax
0x18004d915  lea     r12, RasRtrmgrParamTraceInfo
0x18004d91c  xorps   xmm0, xmm0
0x18004d91f  mov     [rsp+898h+var_850], eax
0x18004d923  mov     [rsp+898h+var_82C], eax
0x18004d927  lea     r13, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18004d92e  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x18004d935  lea     rdi, [rbx+2B0h]
0x18004d93c  movups  [rsp+898h+var_84C], xmm0
0x18004d941  movups  [rsp+898h+var_83C], xmm0
0x18004d946  movups  [rsp+898h+var_860], xmm0
0x18004d94b  test    al, 80h
0x18004d94d  jz      short loc_18004D98E
0x18004d94f  xor     eax, eax
0x18004d951  lea     r9, [rsp+898h+var_860]
0x18004d956  mov     word ptr [rsp+898h+var_850], ax
0x18004d95b  lea     r8, aEnteredActivat_0; "Entered: ActivateRouterDiscovery"
0x18004d962  lea     rax, [rsp+898h+var_850]
0x18004d967  test    rdi, rdi
0x18004d96a  mov     qword ptr [rsp+898h+fResume], rax
0x18004d96f  mov     rdx, r12
0x18004d972  mov     rax, [rbx+48h]
0x18004d976  cmovnz  r9, rdi
0x18004d97a  mov     rcx, r13
0x18004d97d  mov     [rsp+898h+lpArgToCompletionRoutine], rax
0x18004d982  call    McTemplateU0zjzz_EventWriteTransfer
0x18004d987  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x18004d98e  cmp     dword ptr [rbx+0A8h], 3
0x18004d995  jnb     short loc_18004D9B7
0x18004d997  test    al, 80h
0x18004d999  jz      loc_18004DC2A
0x18004d99f  xor     eax, eax
0x18004d9a1  lea     r9, [rsp+898h+var_860]
0x18004d9a6  test    rdi, rdi
0x18004d9a9  mov     word ptr [rsp+898h+var_850], ax
0x18004d9ae  cmovnz  r9, rdi
0x18004d9b2  jmp     loc_18004DC05
0x18004d9b7  cmp     dword ptr [rbx+0DCh], 0
0x18004d9be  jz      short loc_18004D997
0x18004d9c0  mov     rcx, rbx
0x18004d9c3  call    CreateSockets
0x18004d9c8  mov     esi, eax
0x18004d9ca  test    eax, eax
0x18004d9cc  jz      loc_18004DA8D
0x18004d9d2  mov     rcx, cs:Microsoft_Windows_RRASEnableBits
0x18004d9d9  test    cl, cl
0x18004d9db  jns     short loc_18004DA42
0x18004d9dd  mov     r8, [rbx+48h]
0x18004d9e1  lea     rdx, aActivaterouter; "ActivateRouterDiscovery: Couldnt create"...
0x18004d9e8  xor     ecx, ecx
0x18004d9ea  mov     r9d, eax
0x18004d9ed  mov     word ptr [rsp+898h+var_828], cx
0x18004d9f2  mov     word ptr [rsp+898h+var_850], cx
0x18004d9f7  lea     rcx, [rsp+898h+var_828]
0x18004d9fc  call    FormatRRASErrorString
0x18004da01  mov     rcx, cs:Microsoft_Windows_RRASEnableBits
0x18004da08  test    cl, cl
0x18004da0a  jns     short loc_18004DA42
0x18004da0c  lea     rax, [rsp+898h+var_850]
0x18004da11  test    rdi, rdi
0x18004da14  mov     qword ptr [rsp+898h+fResume], rax
0x18004da19  lea     r9, [rsp+898h+var_860]
0x18004da1e  mov     rax, [rbx+48h]
0x18004da22  lea     r8, [rsp+898h+var_828]
0x18004da27  cmovnz  r9, rdi
0x18004da2b  mov     [rsp+898h+lpArgToCompletionRoutine], rax
0x18004da30  mov     rdx, r12
0x18004da33  mov     rcx, r13
0x18004da36  call    McTemplateU0zjzz_EventWriteTransfer
0x18004da3b  mov     rcx, cs:Microsoft_Windows_RRASEnableBits
0x18004da42  test    cl, 80h
0x18004da45  jz      short loc_18004DA86
0x18004da47  xor     eax, eax
0x18004da49  lea     r9, [rsp+898h+var_860]
0x18004da4e  mov     word ptr [rsp+898h+var_850], ax
0x18004da53  lea     r8, aLeavingActivat_2; "Leaving: ActivateRouterDiscovery"
0x18004da5a  lea     rax, [rbx+2B0h]
0x18004da61  mov     rdx, r12
0x18004da64  test    rax, rax
0x18004da67  mov     rcx, r13
0x18004da6a  cmovnz  r9, rax
0x18004da6e  lea     rax, [rsp+898h+var_850]
0x18004da73  mov     qword ptr [rsp+898h+fResume], rax
0x18004da78  mov     rax, [rbx+48h]
0x18004da7c  mov     [rsp+898h+lpArgToCompletionRoutine], rax
0x18004da81  call    McTemplateU0zjzz_EventWriteTransfer
0x18004da86  mov     eax, esi
0x18004da88  jmp     loc_18004DC2C
0x18004da8d  mov     rcx, rbx
0x18004da90  call    UpdateAdvertisement
0x18004da95  mov     esi, eax
0x18004da97  mov     rcx, rbx
0x18004da9a  test    eax, eax
0x18004da9c  jz      short loc_18004DAD3
0x18004da9e  call    DeleteSockets
0x18004daa3  mov     rcx, cs:Microsoft_Windows_RRASEnableBits
0x18004daaa  test    cl, cl
0x18004daac  jns     short loc_18004DA42
0x18004daae  xor     ecx, ecx
0x18004dab0  lea     rdx, aActivaterouter_1; "ActivateRouterDiscovery: Couldnt update"...
0x18004dab7  mov     word ptr [rsp+898h+var_828], cx
0x18004dabc  mov     r8d, esi
0x18004dabf  mov     word ptr [rsp+898h+var_850], cx
0x18004dac4  lea     rcx, [rsp+898h+var_828]
0x18004dac9  call    FormatRRASErrorString
0x18004dace  jmp     loc_18004DA01
0x18004dad3  call    SetFiringTimeForAdvt
0x18004dad8  test    eax, eax
0x18004dada  jz      loc_18004DBD8
0x18004dae0  mov     rcx, cs:g_hRtrDiscTimer; hTimer
0x18004dae7  lea     rdx, [rbx+100h]; lpDueTime
0x18004daee  mov     [rsp+898h+fResume], 0; fResume
0x18004daf6  xor     r9d, r9d; pfnCompletionRoutine
0x18004daf9  xor     r8d, r8d; lPeriod
0x18004dafc  mov     [rsp+898h+lpArgToCompletionRoutine], 0; lpArgToCompletionRoutine
0x18004db05  call    cs:__imp_SetWaitableTimer
0x18004db0b  test    eax, eax
0x18004db0d  jnz     loc_18004DBD8
0x18004db13  call    cs:__imp_GetLastError
0x18004db19  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x18004db20  jge     short loc_18004DB81
0x18004db22  xor     ecx, ecx
0x18004db24  lea     rdx, aActivaterouter_0; "ActivateRouterDiscovery: Error %d setti"...
0x18004db2b  mov     word ptr [rsp+898h+var_828], cx
0x18004db30  mov     r8d, eax
0x18004db33  mov     word ptr [rsp+898h+var_850], cx
0x18004db38  lea     rcx, [rsp+898h+var_828]
0x18004db3d  call    FormatRRASErrorString
0x18004db42  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x18004db49  jge     short loc_18004DB81
0x18004db4b  lea     rax, [rbx+2B0h]
0x18004db52  mov     rdx, r12
0x18004db55  test    rax, rax
0x18004db58  lea     r9, [rsp+898h+var_860]
0x18004db5d  lea     r8, [rsp+898h+var_828]
0x18004db62  mov     rcx, r13
0x18004db65  cmovnz  r9, rax
0x18004db69  lea     rax, [rsp+898h+var_850]
0x18004db6e  mov     qword ptr [rsp+898h+fResume], rax
0x18004db73  mov     rax, [rbx+48h]
0x18004db77  mov     [rsp+898h+lpArgToCompletionRoutine], rax
0x18004db7c  call    McTemplateU0zjzz_EventWriteTransfer
0x18004db81  mov     rcx, rbx
0x18004db84  call    DeleteSockets
0x18004db89  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x18004db90  jz      short loc_18004DBD1
0x18004db92  xor     eax, eax
0x18004db94  lea     r9, [rsp+898h+var_860]
0x18004db99  mov     word ptr [rsp+898h+var_850], ax
0x18004db9e  lea     r8, aLeavingActivat_2; "Leaving: ActivateRouterDiscovery"
0x18004dba5  lea     rax, [rbx+2B0h]
0x18004dbac  mov     rdx, r12
0x18004dbaf  test    rax, rax
0x18004dbb2  mov     rcx, r13
0x18004dbb5  cmovnz  r9, rax
0x18004dbb9  lea     rax, [rsp+898h+var_850]
0x18004dbbe  mov     qword ptr [rsp+898h+fResume], rax
0x18004dbc3  mov     rax, [rbx+48h]
0x18004dbc7  mov     [rsp+898h+lpArgToCompletionRoutine], rax
0x18004dbcc  call    McTemplateU0zjzz_EventWriteTransfer
0x18004dbd1  mov     eax, 3EBh
0x18004dbd6  jmp     short loc_18004DC2C
0x18004dbd8  mov     dword ptr [rbx+0E0h], 1
0x18004dbe2  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x18004dbe9  jz      short loc_18004DC2A
0x18004dbeb  xor     eax, eax
0x18004dbed  lea     r9, [rsp+898h+var_860]
0x18004dbf2  mov     word ptr [rsp+898h+var_850], ax
0x18004dbf7  lea     rax, [rbx+2B0h]
0x18004dbfe  test    rax, rax
0x18004dc01  cmovnz  r9, rax
0x18004dc05  lea     rax, [rsp+898h+var_850]
0x18004dc0a  mov     rdx, r12
0x18004dc0d  mov     qword ptr [rsp+898h+fResume], rax
0x18004dc12  lea     r8, aLeavingActivat_2; "Leaving: ActivateRouterDiscovery"
0x18004dc19  mov     rax, [rbx+48h]
0x18004dc1d  mov     rcx, r13
0x18004dc20  mov     [rsp+898h+lpArgToCompletionRoutine], rax
0x18004dc25  call    McTemplateU0zjzz_EventWriteTransfer
0x18004dc2a  xor     eax, eax
0x18004dc2c  mov     rcx, [rsp+898h+var_28]
0x18004dc34  xor     rcx, rsp; StackCookie
0x18004dc37  call    __security_check_cookie
0x18004dc3c  lea     r11, [rsp+898h+var_18]
0x18004dc44  mov     rbx, [r11+28h]
0x18004dc48  mov     rsi, [r11+30h]
0x18004dc4c  mov     rsp, r11
0x18004dc4f  pop     r13
0x18004dc51  pop     r12
0x18004dc53  pop     rdi
0x18004dc54  retn
```
