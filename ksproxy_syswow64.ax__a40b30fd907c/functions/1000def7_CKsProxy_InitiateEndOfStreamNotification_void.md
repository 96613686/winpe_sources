# CKsProxy::InitiateEndOfStreamNotification(void *)

- ea: `0x1000def7`
- end: `0x1000e055`
- name: `?InitiateEndOfStreamNotification@CKsProxy@@QAGJPAX@Z`
- size: `350`
- prototype: `unsigned int __fastcall(int, void *, CKsProxy *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x100115a5`

## callees

- `0x1000def7`
- `0x1001f3b0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1000df99`
- `KERNEL32!GetLastError` at `0x1000df99`
- `KERNEL32!SetEvent` at `0x1000dfdc`
- `KERNEL32!SetEvent` at `0x1000e016`
- `KERNEL32!SetEvent` at `0x1000dfdc`
- `KERNEL32!SetEvent` at `0x1000e016`
- `KERNEL32!WaitForSingleObjectEx` at `0x1000dfeb`
- `KERNEL32!WaitForSingleObjectEx` at `0x1000e026`
- `KERNEL32!WaitForSingleObjectEx` at `0x1000dfeb`
- `KERNEL32!WaitForSingleObjectEx` at `0x1000e026`
- `KERNEL32!CloseHandle` at `0x1000e037`
- `KERNEL32!CloseHandle` at `0x1000e037`
- `KERNEL32!CreateThread` at `0x1000df89`
- `KERNEL32!CreateThread` at `0x1000df89`
- `KERNEL32!LeaveCriticalSection` at `0x1000dfa2`
- `KERNEL32!LeaveCriticalSection` at `0x1000e048`
- `KERNEL32!LeaveCriticalSection` at `0x1000dfa2`
- `KERNEL32!LeaveCriticalSection` at `0x1000e048`
- `KERNEL32!EnterCriticalSection` at `0x1000df6e`
- `KERNEL32!EnterCriticalSection` at `0x1000df6e`

## pseudocode

```c
unsigned int __fastcall CKsProxy::InitiateEndOfStreamNotification(int a1, void *a2, CKsProxy *this)
{
  int v4; // eax
  unsigned int v5; // ecx
  int v6; // edi
  struct _RTL_CRITICAL_SECTION *v7; // esi
  HANDLE v8; // eax
  signed int LastError; // edi
  unsigned int result; // eax
  HANDLE *v11; // eax
  HANDLE *v12; // eax
  GUID InBuffer; // [esp+10h] [ebp-28h] BYREF
  int v14; // [esp+20h] [ebp-18h]
  int v15; // [esp+24h] [ebp-14h]
  DWORD ThreadId; // [esp+2Ch] [ebp-Ch] BYREF
  void *v17; // [esp+30h] [ebp-8h]
  DWORD BytesReturned; // [esp+34h] [ebp-4h] BYREF

  v17 = a2;
  BytesReturned = 0;
  v4 = 1;
  v5 = *(_DWORD *)(a1 + 316);
  if ( v5 <= 1 )
  {
LABEL_4:
    InBuffer = _GUID_7f4bcbe0_9ea5_11cf_a5d6_28db04c10000;
    v6 = 0;
    v14 = 4;
    v15 = 512;
    if ( KsSynchronousDeviceControl(a2, 0x2F0007u, &InBuffer, 0x18u, 0, 0, &BytesReturned) >= 0 )
    {
      v7 = *(struct _RTL_CRITICAL_SECTION **)(a1 + 56);
      EnterCriticalSection(v7);
      if ( !*(_DWORD *)(a1 + 304) )
      {
        v8 = CreateThread(0, 0, CKsProxy::WaitThread, (LPVOID)a1, 0, &ThreadId);
        *(_DWORD *)(a1 + 304) = v8;
        if ( !v8 )
        {
          LastError = GetLastError();
          LeaveCriticalSection(v7);
          result = (unsigned __int16)LastError | 0x80070000;
          if ( LastError <= 0 )
            return LastError;
          return result;
        }
      }
      *(_DWORD *)(a1 + 328) = v17;
      v11 = *(HANDLE **)(a1 + 308);
      *(_DWORD *)(a1 + 324) = 1;
      SetEvent(*v11);
      WaitForSingleObjectEx(*(HANDLE *)(a1 + 320), 0xFFFFFFFF, 0);
      v6 = *(_DWORD *)(a1 + 328);
      if ( v6 < 0 && *(_DWORD *)(a1 + 316) == 1 )
      {
        v12 = *(HANDLE **)(a1 + 308);
        *(_DWORD *)(a1 + 324) = 0;
        SetEvent(*v12);
        WaitForSingleObjectEx(*(HANDLE *)(a1 + 304), 0xFFFFFFFF, 0);
        if ( *(_DWORD *)(a1 + 304) )
        {
          CloseHandle(*(HANDLE *)(a1 + 304));
          *(_DWORD *)(a1 + 304) = 0;
        }
      }
      LeaveCriticalSection(v7);
    }
    return v6;
  }
  while ( *(void **)(*(_DWORD *)(a1 + 312) + 4 * v4) != a2 )
  {
    if ( ++v4 >= v5 )
      goto LABEL_4;
  }
  return 0;
}

```

## disassembly

```asm
0x1000def7  mov     edi, edi
0x1000def9  push    ebp
0x1000defa  mov     ebp, esp
0x1000defc  sub     esp, 2Ch
0x1000deff  push    ebx
0x1000df00  mov     ebx, ecx
0x1000df02  mov     [ebp+var_8], edx
0x1000df05  xor     eax, eax
0x1000df07  mov     [ebp+BytesReturned], 0
0x1000df0e  inc     eax
0x1000df0f  push    esi
0x1000df10  mov     ecx, [ebx+13Ch]
0x1000df16  push    edi
0x1000df17  cmp     ecx, eax
0x1000df19  jbe     short loc_1000DF2F
0x1000df1b  mov     esi, [ebx+138h]
0x1000df21  cmp     [esi+eax*4], edx
0x1000df24  jz      loc_1000DFBA
0x1000df2a  inc     eax
0x1000df2b  cmp     eax, ecx
0x1000df2d  jb      short loc_1000DF21
0x1000df2f  mov     esi, offset __GUID_7f4bcbe0_9ea5_11cf_a5d6_28db04c10000
0x1000df34  lea     edi, [ebp+InBuffer]
0x1000df37  lea     eax, [ebp+BytesReturned]
0x1000df3a  push    eax; lpBytesReturned
0x1000df3b  lea     eax, [ebp+InBuffer]
0x1000df3e  movsd
0x1000df3f  movsd
0x1000df40  movsd
0x1000df41  movsd
0x1000df42  xor     edi, edi
0x1000df44  mov     [ebp+var_18], 4
0x1000df4b  push    edi; nOutBufferSize
0x1000df4c  push    edi; lpOutBuffer
0x1000df4d  push    18h; nInBufferSize
0x1000df4f  push    eax; lpInBuffer
0x1000df50  push    2F0007h; dwIoControlCode
0x1000df55  push    edx; hDevice
0x1000df56  mov     [ebp+var_14], 200h
0x1000df5d  call    _KsSynchronousDeviceControl@28; KsSynchronousDeviceControl(x,x,x,x,x,x,x)
0x1000df62  test    eax, eax
0x1000df64  js      loc_1000E04E
0x1000df6a  mov     esi, [ebx+38h]
0x1000df6d  push    esi; lpCriticalSection
0x1000df6e  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x1000df74  cmp     [ebx+130h], edi
0x1000df7a  jnz     short loc_1000DFC1
0x1000df7c  lea     eax, [ebp+ThreadId]
0x1000df7f  push    eax; lpThreadId
0x1000df80  push    edi; dwCreationFlags
0x1000df81  push    ebx; lpParameter
0x1000df82  push    offset ?WaitThread@CKsProxy@@SGKPAV1@@Z; lpStartAddress
0x1000df87  push    edi; dwStackSize
0x1000df88  push    edi; lpThreadAttributes
0x1000df89  call    ds:__imp__CreateThread@24; CreateThread(x,x,x,x,x,x)
0x1000df8f  mov     [ebx+130h], eax
0x1000df95  test    eax, eax
0x1000df97  jnz     short loc_1000DFC1
0x1000df99  call    ds:__imp__GetLastError@0; GetLastError()
0x1000df9f  push    esi; lpCriticalSection
0x1000dfa0  mov     edi, eax
0x1000dfa2  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1000dfa8  movzx   eax, di
0x1000dfab  or      eax, 80070000h
0x1000dfb0  test    edi, edi
0x1000dfb2  cmovle  eax, edi
0x1000dfb5  jmp     loc_1000E050
0x1000dfba  xor     eax, eax
0x1000dfbc  jmp     loc_1000E050
0x1000dfc1  mov     eax, [ebp+var_8]
0x1000dfc4  mov     [ebx+148h], eax
0x1000dfca  mov     eax, [ebx+134h]
0x1000dfd0  mov     dword ptr [ebx+144h], 1
0x1000dfda  push    dword ptr [eax]; hEvent
0x1000dfdc  call    ds:__imp__SetEvent@4; SetEvent(x)
0x1000dfe2  push    edi; bAlertable
0x1000dfe3  push    0FFFFFFFFh; dwMilliseconds
0x1000dfe5  push    dword ptr [ebx+140h]; hHandle
0x1000dfeb  call    ds:__imp__WaitForSingleObjectEx@12; WaitForSingleObjectEx(x,x,x)
0x1000dff1  mov     edi, [ebx+148h]
0x1000dff7  test    edi, edi
0x1000dff9  jns     short loc_1000E047
0x1000dffb  cmp     dword ptr [ebx+13Ch], 1
0x1000e002  jnz     short loc_1000E047
0x1000e004  mov     eax, [ebx+134h]
0x1000e00a  mov     dword ptr [ebx+144h], 0
0x1000e014  push    dword ptr [eax]; hEvent
0x1000e016  call    ds:__imp__SetEvent@4; SetEvent(x)
0x1000e01c  push    0; bAlertable
0x1000e01e  push    0FFFFFFFFh; dwMilliseconds
0x1000e020  push    dword ptr [ebx+130h]; hHandle
0x1000e026  call    ds:__imp__WaitForSingleObjectEx@12; WaitForSingleObjectEx(x,x,x)
0x1000e02c  mov     eax, [ebx+130h]
0x1000e032  test    eax, eax
0x1000e034  jz      short loc_1000E047
0x1000e036  push    eax; hObject
0x1000e037  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x1000e03d  mov     dword ptr [ebx+130h], 0
0x1000e047  push    esi; lpCriticalSection
0x1000e048  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1000e04e  mov     eax, edi
0x1000e050  pop     edi
0x1000e051  pop     esi
0x1000e052  pop     ebx
0x1000e053  leave
0x1000e054  retn
```
