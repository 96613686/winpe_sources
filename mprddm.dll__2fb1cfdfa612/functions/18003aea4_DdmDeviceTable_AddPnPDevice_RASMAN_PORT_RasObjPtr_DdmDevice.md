# DdmDeviceTable::AddPnPDevice(_RASMAN_PORT *,RasObjPtr<DdmDevice> &)

- ea: `0x18003aea4`
- end: `0x18003b327`
- name: `?AddPnPDevice@DdmDeviceTable@@QEAAKPEAU_RASMAN_PORT@@AEAV?$RasObjPtr@VDdmDevice@@@@@Z`
- size: `1155`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18003ba98`
- `0x180047d20`

## callees

- `0x180007c50`
- `0x18003ab88`
- `0x18003aea4`
- `0x18003b330`
- `0x18003b7a8`
- `0x180071cec`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008e010`

## import_xrefs

- `msvcrt!_itow_s` at `0x18003af6f`
- `msvcrt!_itow_s` at `0x18003b017`
- `msvcrt!_itow_s` at `0x18003b19f`
- `msvcrt!_itow_s` at `0x18003b281`
- `msvcrt!_itow_s` at `0x18003af6f`
- `msvcrt!_itow_s` at `0x18003b017`
- `msvcrt!_itow_s` at `0x18003b19f`
- `msvcrt!_itow_s` at `0x18003b281`
- `KERNEL32!MultiByteToWideChar` at `0x18003b0bd`
- `KERNEL32!MultiByteToWideChar` at `0x18003b0bd`
- `KERNEL32!LeaveCriticalSection` at `0x18003b256`
- `KERNEL32!LeaveCriticalSection` at `0x18003b256`
- `KERNEL32!EnterCriticalSection` at `0x18003b1fd`
- `KERNEL32!EnterCriticalSection` at `0x18003b1fd`
- `rtutils!RouterLogEventW` at `0x18003b14f`
- `rtutils!RouterLogEventW` at `0x18003b14f`
- `rtutils!RouterLogEventStringW` at `0x18003b105`
- `rtutils!RouterLogEventStringW` at `0x18003b105`
- `rasman!RasPortOpen` at `0x18003b089`
- `rasman!RasPortOpen` at `0x18003b089`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DdmDeviceTable::AddPnPDevice(DdmDeviceTable *a1, _QWORD *a2)
{
  DWORD v4; // r15d
  LPWSTR v6; // rbx
  char v7; // al
  __int64 v8; // rcx
  DWORD v9; // eax
  __int64 v10; // rdx
  LPWSTR plpszSubStringArray; // [rsp+40h] [rbp-C0h] BYREF
  int Value[2]; // [rsp+48h] [rbp-B8h] BYREF
  LPCCH lpMultiByteStr; // [rsp+50h] [rbp-B0h]
  DdmDeviceTable *v14; // [rsp+58h] [rbp-A8h]
  __int128 v15; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t Buffer[2]; // [rsp+70h] [rbp-90h] BYREF
  __int128 v17; // [rsp+74h] [rbp-8Ch]
  __int128 v18; // [rsp+84h] [rbp-7Ch]
  int v19; // [rsp+94h] [rbp-6Ch]
  WCHAR WideCharStr[20]; // [rsp+98h] [rbp-68h] BYREF
  int v21; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v22[2044]; // [rsp+C4h] [rbp-3Ch] BYREF

  v14 = a1;
  v4 = 0;
  *(_QWORD *)Value = 0;
  plpszSubStringArray = 0;
  v21 = 0;
  memset_0(v22, 0, sizeof(v22));
  *(_DWORD *)Buffer = 0;
  v17 = 0;
  v18 = 0;
  v19 = 0;
  v15 = 0;
  if ( dword_1800C8654 )
    return 50;
  DdmDeviceTable::FindDevice(a1, *a2, &plpszSubStringArray);
  v6 = plpszSubStringArray;
  if ( plpszSubStringArray )
  {
    if ( (byte_1800C8404 & 8) != 0 )
    {
      LOWORD(v21) = 0;
      Buffer[0] = 0;
      if ( *(_DWORD *)a2 != -1 )
        _itow_s(*(_DWORD *)a2, Buffer, 0x14u, 10);
      FormatRRASErrorString(&v21, L"Error:Recvd add new port notification for existing port %d", *a2);
      if ( (byte_1800C8404 & 8) != 0 )
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasDdmParamTraceError,
          (unsigned int)&v21,
          (unsigned int)&v15,
          0,
          (__int64)Buffer);
    }
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v6 + 2, 0xFFFFFFFF) == 1 )
    {
      if ( v6 )
        (**(void (__fastcall ***)(LPWSTR, __int64))v6)(v6, 1);
    }
    return 183;
  }
  v7 = byte_1800C8404;
  if ( (byte_1800C8404 & 8) != 0 )
  {
    LOWORD(v21) = 0;
    Buffer[0] = 0;
    if ( *(_DWORD *)a2 != -1 )
      _itow_s(*(_DWORD *)a2, Buffer, 0x14u, 10);
    FormatRRASErrorString(&v21, L"Adding new port hPort=%d", *a2);
    v7 = byte_1800C8404;
    if ( (byte_1800C8404 & 8) != 0 )
    {
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasDdmParamTraceError,
        (unsigned int)&v21,
        (unsigned int)&v15,
        0,
        (__int64)Buffer);
      v7 = byte_1800C8404;
    }
  }
  if ( (a2[4] & 5) == 0 )
  {
    if ( (v7 & 8) != 0 )
    {
      LOWORD(v21) = 0;
      Buffer[0] = 0;
      if ( *(_DWORD *)a2 != -1 )
        _itow_s(*(_DWORD *)a2, Buffer, 0x14u, 10);
      FormatRRASErrorString(
        &v21,
        L"Conf. usage wrong, not adding port hPort=%d usage=%d",
        *a2,
        *((unsigned int *)a2 + 8));
      if ( (byte_1800C8404 & 8) != 0 )
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasDdmParamTraceError,
          (unsigned int)&v21,
          (unsigned int)&v15,
          0,
          (__int64)Buffer);
    }
    goto LABEL_42;
  }
  lpMultiByteStr = (LPCCH)(a2 + 1);
  v4 = RasPortOpen(a2 + 1, Value, 0);
  if ( v4 )
  {
    plpszSubStringArray = 0;
    MultiByteToWideChar(0, 0, lpMultiByteStr, -1, WideCharStr, 17);
    plpszSubStringArray = WideCharStr;
    if ( dword_1800C84E4 )
      RouterLogEventStringW(hLogHandle, 1u, 0x4E8Cu, 1u, &plpszSubStringArray, v4, 1u);
  }
  else
  {
    v9 = DdmDeviceTable::CreateNewDevice(v8, *(_QWORD *)Value, a2, &plpszSubStringArray);
    v4 = v9;
    if ( v9 )
    {
      if ( dword_1800C84E4 )
        RouterLogEventW(hLogHandle, 1u, 0x4E88u, 0, 0, v9);
    }
    else
    {
      v4 = DdmDeviceTable::AddDevice(v14);
      if ( !v4 )
      {
        v6 = plpszSubStringArray;
        EnterCriticalSection((LPCRITICAL_SECTION)(plpszSubStringArray + 8));
        ((void (*)(void))qword_1800C8570)();
        if ( (*((_DWORD *)v6 + 34) & 0xFFFF0000) != 0x20000 )
        {
          LOBYTE(v10) = 1;
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)g_pIDimInterfaceTable + 32LL))(
            g_pIDimInterfaceTable,
            v10);
        }
        if ( v6[68] != 13 )
          (*(void (__fastcall **)(LPWSTR))(*(_QWORD *)v6 + 168LL))(v6);
        LeaveCriticalSection((LPCRITICAL_SECTION)(v6 + 8));
        goto LABEL_42;
      }
      if ( (byte_1800C8404 & 8) != 0 )
      {
        LOWORD(v21) = 0;
        Buffer[0] = 0;
        if ( Value[0] != -1 )
          _itow_s(Value[0], Buffer, 0x14u, 10);
        FormatRRASErrorString(&v21, L"AddDevice failed for port hPort=%d. Error: %d", *a2, v4);
        if ( (byte_1800C8404 & 8) != 0 )
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasDdmParamTraceError,
            (unsigned int)&v21,
            (unsigned int)&v15,
            0,
            (__int64)Buffer);
      }
    }
    v6 = plpszSubStringArray;
  }
LABEL_42:
  if ( v6 && _InterlockedExchangeAdd((volatile signed __int32 *)v6 + 2, 0xFFFFFFFF) == 1 )
    (**(void (__fastcall ***)(LPWSTR, __int64))v6)(v6, 1);
  return v4;
}

```

## disassembly

```asm
0x18003aea4  mov     [rsp-8+arg_10], rbx
0x18003aea9  push    rbp
0x18003aeaa  push    rdi
0x18003aeab  push    r15
0x18003aead  lea     rbp, [rsp-7D0h]
0x18003aeb5  sub     rsp, 8D0h
0x18003aebc  mov     rax, cs:__security_cookie
0x18003aec3  xor     rax, rsp
0x18003aec6  mov     [rbp+7E0h+var_20], rax
0x18003aecd  mov     rdi, rdx
0x18003aed0  mov     rbx, rcx
0x18003aed3  mov     [rsp+8E0h+var_888], rcx
0x18003aed8  xor     r15d, r15d
0x18003aedb  mov     qword ptr [rsp+8E0h+Value], r15
0x18003aee0  mov     [rsp+8E0h+plpszSubStringArray], r15
0x18003aee5  mov     [rbp+7E0h+var_820], r15d
0x18003aee9  xor     edx, edx; Val
0x18003aeeb  mov     r8d, 7FCh; Size
0x18003aef1  lea     rcx, [rbp+7E0h+var_81C]; void *
0x18003aef5  call    memset_0
0x18003aefa  mov     dword ptr [rsp+8E0h+Buffer], r15d
0x18003aeff  xorps   xmm0, xmm0
0x18003af02  xor     eax, eax
0x18003af04  movups  [rsp+8E0h+var_86C], xmm0
0x18003af09  movups  [rbp+7E0h+var_85C], xmm0
0x18003af0d  mov     [rbp+7E0h+var_84C], eax
0x18003af10  movups  [rsp+8E0h+var_880], xmm0
0x18003af15  cmp     cs:dword_1800C8654, r15d
0x18003af1c  jz      short loc_18003AF27
0x18003af1e  lea     eax, [r15+32h]
0x18003af22  jmp     loc_18003B304
0x18003af27  lea     r8, [rsp+8E0h+plpszSubStringArray]
0x18003af2c  mov     rdx, [rdi]
0x18003af2f  mov     rcx, rbx
0x18003af32  call    ?FindDevice@DdmDeviceTable@@QEAAXPEAXAEAV?$RasObjPtr@VDdmDevice@@@@@Z; DdmDeviceTable::FindDevice(void *,RasObjPtr<DdmDevice> &)
0x18003af37  mov     rbx, [rsp+8E0h+plpszSubStringArray]
0x18003af3c  test    rbx, rbx
0x18003af3f  jz      loc_18003AFEC
0x18003af45  test    cs:byte_1800C8404, 8
0x18003af4c  jz      short loc_18003AFBD
0x18003af4e  mov     word ptr [rbp+7E0h+var_820], r15w
0x18003af53  mov     [rsp+8E0h+Buffer], r15w
0x18003af59  cmp     dword ptr [rdi], 0FFFFFFFFh
0x18003af5c  jz      short loc_18003AF75
0x18003af5e  mov     r9d, 0Ah; Radix
0x18003af64  lea     r8d, [r9+0Ah]; BufferCount
0x18003af68  lea     rdx, [rsp+8E0h+Buffer]; Buffer
0x18003af6d  mov     ecx, [rdi]; Value
0x18003af6f  call    cs:__imp__itow_s
0x18003af75  mov     r8, [rdi]
0x18003af78  lea     rdx, aErrorRecvdAddN; "Error:Recvd add new port notification f"...
0x18003af7f  lea     rcx, [rbp+7E0h+var_820]
0x18003af83  call    FormatRRASErrorString
0x18003af88  test    cs:byte_1800C8404, 8
0x18003af8f  jz      short loc_18003AFBD
0x18003af91  lea     rax, [rsp+8E0h+Buffer]
0x18003af96  mov     qword ptr [rsp+8E0h+cchWideChar], rax
0x18003af9b  mov     [rsp+8E0h+lpWideCharStr], r15
0x18003afa0  lea     r9, [rsp+8E0h+var_880]
0x18003afa5  lea     r8, [rbp+7E0h+var_820]
0x18003afa9  lea     rdx, RasDdmParamTraceError
0x18003afb0  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18003afb7  call    McTemplateU0zjzz_EventWriteTransfer
0x18003afbc  nop
0x18003afbd  or      eax, 0FFFFFFFFh
0x18003afc0  lock xadd [rbx+8], eax
0x18003afc5  cmp     eax, 1
0x18003afc8  jnz     short loc_18003AFE2
0x18003afca  test    rbx, rbx
0x18003afcd  jz      short loc_18003AFE2
0x18003afcf  mov     rax, [rbx]
0x18003afd2  mov     edx, 1
0x18003afd7  mov     rcx, rbx
0x18003afda  mov     rax, [rax]
0x18003afdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003afe2  mov     eax, 0B7h
0x18003afe7  jmp     loc_18003B304
0x18003afec  mov     al, cs:byte_1800C8404
0x18003aff2  test    al, 8
0x18003aff4  jz      short loc_18003B06B
0x18003aff6  mov     word ptr [rbp+7E0h+var_820], r15w
0x18003affb  mov     [rsp+8E0h+Buffer], r15w
0x18003b001  cmp     dword ptr [rdi], 0FFFFFFFFh
0x18003b004  jz      short loc_18003B01D
0x18003b006  mov     r9d, 0Ah; Radix
0x18003b00c  lea     r8d, [r9+0Ah]; BufferCount
0x18003b010  lea     rdx, [rsp+8E0h+Buffer]; Buffer
0x18003b015  mov     ecx, [rdi]; Value
0x18003b017  call    cs:__imp__itow_s
0x18003b01d  mov     r8, [rdi]
0x18003b020  lea     rdx, aAddingNewPortH; "Adding new port hPort=%d"
0x18003b027  lea     rcx, [rbp+7E0h+var_820]
0x18003b02b  call    FormatRRASErrorString
0x18003b030  mov     al, cs:byte_1800C8404
0x18003b036  test    al, 8
0x18003b038  jz      short loc_18003B06B
0x18003b03a  lea     rax, [rsp+8E0h+Buffer]
0x18003b03f  mov     qword ptr [rsp+8E0h+cchWideChar], rax
0x18003b044  mov     [rsp+8E0h+lpWideCharStr], r15
0x18003b049  lea     r9, [rsp+8E0h+var_880]
0x18003b04e  lea     r8, [rbp+7E0h+var_820]
0x18003b052  lea     rdx, RasDdmParamTraceError
0x18003b059  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18003b060  call    McTemplateU0zjzz_EventWriteTransfer
0x18003b065  mov     al, cs:byte_1800C8404
0x18003b06b  test    byte ptr [rdi+20h], 5
0x18003b06f  jz      loc_18003B25E
0x18003b075  lea     rax, [rdi+8]
0x18003b079  mov     [rsp+8E0h+lpMultiByteStr], rax
0x18003b07e  xor     r8d, r8d
0x18003b081  lea     rdx, [rsp+8E0h+Value]
0x18003b086  mov     rcx, rax
0x18003b089  call    cs:__imp_RasPortOpen
0x18003b08f  mov     r15d, eax
0x18003b092  test    eax, eax
0x18003b094  jz      short loc_18003B110
0x18003b096  mov     [rsp+8E0h+plpszSubStringArray], 0
0x18003b09f  mov     [rsp+8E0h+cchWideChar], 11h; cchWideChar
0x18003b0a7  lea     rax, [rbp+7E0h+WideCharStr]
0x18003b0ab  mov     [rsp+8E0h+lpWideCharStr], rax; lpWideCharStr
0x18003b0b0  or      r9d, 0FFFFFFFFh; cbMultiByte
0x18003b0b4  mov     r8, [rsp+8E0h+lpMultiByteStr]; lpMultiByteStr
0x18003b0b9  xor     edx, edx; dwFlags
0x18003b0bb  xor     ecx, ecx; CodePage
0x18003b0bd  call    cs:__imp_MultiByteToWideChar
0x18003b0c3  lea     rax, [rbp+7E0h+WideCharStr]
0x18003b0c7  mov     [rsp+8E0h+plpszSubStringArray], rax
0x18003b0cc  cmp     cs:dword_1800C84E4, 0
0x18003b0d3  jbe     loc_18003B2D7
0x18003b0d9  mov     [rsp+8E0h+dwErrorIndex], 1; dwErrorIndex
0x18003b0e1  mov     [rsp+8E0h+cchWideChar], r15d; dwErrorCode
0x18003b0e6  lea     rax, [rsp+8E0h+plpszSubStringArray]
0x18003b0eb  mov     [rsp+8E0h+lpWideCharStr], rax; plpszSubStringArray
0x18003b0f0  mov     edx, 1; dwEventType
0x18003b0f5  mov     r9d, edx; dwSubStringCount
0x18003b0f8  mov     r8d, 4E8Ch; dwMessageId
0x18003b0fe  mov     rcx, cs:hLogHandle; hLogHandle
0x18003b105  call    cs:__imp_RouterLogEventStringW
0x18003b10b  jmp     loc_18003B2D7
0x18003b110  lea     r9, [rsp+8E0h+plpszSubStringArray]
0x18003b115  mov     r8, rdi
0x18003b118  mov     rdx, qword ptr [rsp+8E0h+Value]
0x18003b11d  call    ?CreateNewDevice@DdmDeviceTable@@QEAAKPEAXPEAU_RASMAN_PORT@@AEAV?$RasObjPtr@VDdmDevice@@@@@Z; DdmDeviceTable::CreateNewDevice(void *,_RASMAN_PORT *,RasObjPtr<DdmDevice> &)
0x18003b122  mov     r15d, eax
0x18003b125  xor     ebx, ebx
0x18003b127  test    eax, eax
0x18003b129  jz      short loc_18003B15F
0x18003b12b  cmp     cs:dword_1800C84E4, ebx
0x18003b131  jbe     short loc_18003B155
0x18003b133  mov     [rsp+8E0h+cchWideChar], eax; dwErrorCode
0x18003b137  mov     [rsp+8E0h+lpWideCharStr], rbx; plpszSubStringArray
0x18003b13c  xor     r9d, r9d; dwSubStringCount
0x18003b13f  lea     edx, [rbx+1]; dwEventType
0x18003b142  mov     r8d, 4E88h; dwMessageId
0x18003b148  mov     rcx, cs:hLogHandle; hLogHandle
0x18003b14f  call    cs:__imp_RouterLogEventW
0x18003b155  mov     rbx, [rsp+8E0h+plpszSubStringArray]
0x18003b15a  jmp     loc_18003B2D7
0x18003b15f  lea     rdx, [rsp+8E0h+plpszSubStringArray]
0x18003b164  mov     rcx, [rsp+8E0h+var_888]; this
0x18003b169  call    ?AddDevice@DdmDeviceTable@@QEAAKAEAV?$RasObjPtr@VDdmDevice@@@@@Z; DdmDeviceTable::AddDevice(RasObjPtr<DdmDevice> &)
0x18003b16e  mov     r15d, eax
0x18003b171  test    eax, eax
0x18003b173  jz      short loc_18003B1F4
0x18003b175  test    cs:byte_1800C8404, 8
0x18003b17c  jz      short loc_18003B155
0x18003b17e  mov     word ptr [rbp+7E0h+var_820], bx
0x18003b182  mov     [rsp+8E0h+Buffer], bx
0x18003b187  mov     ecx, [rsp+8E0h+Value]; Value
0x18003b18b  cmp     ecx, 0FFFFFFFFh
0x18003b18e  jz      short loc_18003B1A5
0x18003b190  mov     r9d, 0Ah; Radix
0x18003b196  lea     r8d, [r9+0Ah]; BufferCount
0x18003b19a  lea     rdx, [rsp+8E0h+Buffer]; Buffer
0x18003b19f  call    cs:__imp__itow_s
0x18003b1a5  mov     r9d, r15d
0x18003b1a8  mov     r8, [rdi]
0x18003b1ab  lea     rdx, aAdddeviceFaile; "AddDevice failed for port hPort=%d. Err"...
0x18003b1b2  lea     rcx, [rbp+7E0h+var_820]
0x18003b1b6  call    FormatRRASErrorString
0x18003b1bb  test    cs:byte_1800C8404, 8
0x18003b1c2  jz      short loc_18003B155
0x18003b1c4  lea     rax, [rsp+8E0h+Buffer]
0x18003b1c9  mov     qword ptr [rsp+8E0h+cchWideChar], rax
0x18003b1ce  mov     [rsp+8E0h+lpWideCharStr], rbx
0x18003b1d3  lea     r9, [rsp+8E0h+var_880]
0x18003b1d8  lea     r8, [rbp+7E0h+var_820]
0x18003b1dc  lea     rdx, RasDdmParamTraceError
0x18003b1e3  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18003b1ea  call    McTemplateU0zjzz_EventWriteTransfer
0x18003b1ef  jmp     loc_18003B155
0x18003b1f4  mov     rbx, [rsp+8E0h+plpszSubStringArray]
0x18003b1f9  lea     rcx, [rbx+10h]; lpCriticalSection
0x18003b1fd  call    cs:__imp_EnterCriticalSection
0x18003b203  mov     rax, cs:qword_1800C8570
0x18003b20a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b20f  mov     eax, [rbx+88h]
0x18003b215  and     eax, 0FFFF0000h
0x18003b21a  cmp     eax, 20000h
0x18003b21f  jz      short loc_18003B236
0x18003b221  mov     rcx, cs:g_pIDimInterfaceTable
0x18003b228  mov     rax, [rcx]
0x18003b22b  mov     dl, 1
0x18003b22d  mov     rax, [rax+20h]
0x18003b231  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b236  cmp     word ptr [rbx+88h], 0Dh
0x18003b23e  jz      short loc_18003B252
0x18003b240  mov     rax, [rbx]
0x18003b243  mov     rcx, rbx
0x18003b246  mov     rax, [rax+0A8h]
0x18003b24d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b252  lea     rcx, [rbx+10h]; lpCriticalSection
0x18003b256  call    cs:__imp_LeaveCriticalSection
0x18003b25c  jmp     short loc_18003B2D7
0x18003b25e  test    al, 8
0x18003b260  jz      short loc_18003B2D7
0x18003b262  xor     eax, eax
0x18003b264  mov     word ptr [rbp+7E0h+var_820], ax
0x18003b268  mov     [rsp+8E0h+Buffer], ax
0x18003b26d  cmp     dword ptr [rdi], 0FFFFFFFFh
0x18003b270  jz      short loc_18003B287
0x18003b272  lea     r9d, [rax+0Ah]; Radix
0x18003b276  lea     r8d, [rax+14h]; BufferCount
0x18003b27a  lea     rdx, [rsp+8E0h+Buffer]; Buffer
0x18003b27f  mov     ecx, [rdi]; Value
0x18003b281  call    cs:__imp__itow_s
0x18003b287  mov     r9d, [rdi+20h]
0x18003b28b  mov     r8, [rdi]
0x18003b28e  lea     rdx, aConfUsageWrong; "Conf. usage wrong, not adding port hPor"...
0x18003b295  lea     rcx, [rbp+7E0h+var_820]
0x18003b299  call    FormatRRASErrorString
0x18003b29e  test    cs:byte_1800C8404, 8
0x18003b2a5  jz      short loc_18003B2D7
0x18003b2a7  lea     rax, [rsp+8E0h+Buffer]
0x18003b2ac  mov     qword ptr [rsp+8E0h+cchWideChar], rax
0x18003b2b1  mov     [rsp+8E0h+lpWideCharStr], 0
0x18003b2ba  lea     r9, [rsp+8E0h+var_880]
0x18003b2bf  lea     r8, [rbp+7E0h+var_820]
0x18003b2c3  lea     rdx, RasDdmParamTraceError
0x18003b2ca  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18003b2d1  call    McTemplateU0zjzz_EventWriteTransfer
0x18003b2d6  nop
0x18003b2d7  test    rbx, rbx
0x18003b2da  jz      short loc_18003B301
0x18003b2dc  or      eax, 0FFFFFFFFh
0x18003b2df  lock xadd [rbx+8], eax
0x18003b2e4  cmp     eax, 1
0x18003b2e7  jnz     short loc_18003B301
0x18003b2e9  test    rbx, rbx
0x18003b2ec  jz      short loc_18003B301
0x18003b2ee  mov     rax, [rbx]
0x18003b2f1  mov     edx, 1
0x18003b2f6  mov     rcx, rbx
0x18003b2f9  mov     rax, [rax]
0x18003b2fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b301  mov     eax, r15d
0x18003b304  mov     rcx, [rbp+7E0h+var_20]
0x18003b30b  xor     rcx, rsp; StackCookie
0x18003b30e  call    __security_check_cookie
0x18003b313  mov     rbx, [rsp+8E0h+arg_10]
0x18003b31b  add     rsp, 8D0h
0x18003b322  pop     r15
0x18003b324  pop     rdi
0x18003b325  pop     rbp
0x18003b326  retn
```
