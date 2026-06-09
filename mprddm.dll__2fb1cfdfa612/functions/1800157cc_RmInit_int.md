# RmInit(int *)

- ea: `0x1800157cc`
- end: `0x180015bee`
- name: `?RmInit@@YAKPEAH@Z`
- size: `1058`
- prototype: `unsigned int __fastcall(int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18001b570`

## callees

- `0x180007b7c`
- `0x1800157cc`
- `0x18002e268`
- `0x18003ab88`
- `0x18003b330`
- `0x18003b8f4`
- `0x180071cec`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008e010`

## import_xrefs

- `KERNEL32!MultiByteToWideChar` at `0x1800159fa`
- `KERNEL32!MultiByteToWideChar` at `0x1800159fa`
- `KERNEL32!Sleep` at `0x1800158a0`
- `KERNEL32!Sleep` at `0x1800158a0`
- `KERNEL32!HeapAlloc` at `0x18001588a`
- `KERNEL32!HeapAlloc` at `0x18001588a`
- `KERNEL32!GetLastError` at `0x1800158d3`
- `KERNEL32!GetLastError` at `0x18001590b`
- `KERNEL32!GetLastError` at `0x1800158d3`
- `KERNEL32!GetLastError` at `0x18001590b`
- `KERNEL32!LeaveCriticalSection` at `0x180015ac2`
- `KERNEL32!LeaveCriticalSection` at `0x180015ac2`
- `KERNEL32!EnterCriticalSection` at `0x180015a9b`
- `KERNEL32!EnterCriticalSection` at `0x180015a9b`
- `KERNEL32!HeapFree` at `0x180015873`
- `KERNEL32!HeapFree` at `0x180015bc3`
- `KERNEL32!HeapFree` at `0x180015873`
- `KERNEL32!HeapFree` at `0x180015bc3`
- `rtutils!RouterLogEventW` at `0x180015900`
- `rtutils!RouterLogEventW` at `0x180015934`
- `rtutils!RouterLogEventW` at `0x180015bab`
- `rtutils!RouterLogEventW` at `0x180015900`
- `rtutils!RouterLogEventW` at `0x180015934`
- `rtutils!RouterLogEventW` at `0x180015bab`
- `rtutils!RouterLogEventStringW` at `0x18001596f`
- `rtutils!RouterLogEventStringW` at `0x180015a3c`
- `rtutils!RouterLogEventStringW` at `0x18001596f`
- `rtutils!RouterLogEventStringW` at `0x180015a3c`
- `rasman!RasPortOpen` at `0x1800159cc`
- `rasman!RasPortOpen` at `0x1800159cc`
- `rasman!RasPortEnum` at `0x180015844`
- `rasman!RasPortEnum` at `0x180015844`
- `sstpcfg!SetupSstpServerConfig` at `0x1800159b0`
- `sstpcfg!SetupSstpServerConfig` at `0x1800159b0`

## string_xrefs

- `0x180015b22`: `DDMServiceInitialize: SetupSstpServerConfig failed. Error %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RmInit(int *a1)
{
  char *v2; // r14
  int v3; // edi
  DWORD v4; // ebx
  unsigned int v5; // ecx
  DWORD LastError; // eax
  DWORD dwErrorCode; // eax
  int v8; // r12d
  char *v9; // r15
  __int64 v10; // rsi
  DWORD v11; // eax
  LPWSTR v12; // rdi
  __int64 v13; // rcx
  DdmDeviceTable *Instance; // rax
  __int64 v15; // r8
  unsigned int v17; // [rsp+40h] [rbp-C0h] BYREF
  LPWSTR plpszSubStringArray; // [rsp+48h] [rbp-B8h] BYREF
  SIZE_T dwBytes; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v20; // [rsp+58h] [rbp-A8h] BYREF
  int *v21; // [rsp+60h] [rbp-A0h]
  WCHAR WideCharStr[8]; // [rsp+68h] [rbp-98h] BYREF
  int *v23; // [rsp+78h] [rbp-88h]
  int v24; // [rsp+80h] [rbp-80h]
  int v25; // [rsp+84h] [rbp-7Ch]
  int v26; // [rsp+90h] [rbp-70h] BYREF
  char v27[2044]; // [rsp+94h] [rbp-6Ch] BYREF

  v21 = a1;
  v20 = 0;
  v2 = 0;
  LODWORD(dwBytes) = 0;
  v17 = 0;
  v3 = 100;
  v26 = 0;
  memset_0(v27, 0, sizeof(v27));
  *a1 = 0;
  while ( 1 )
  {
    v4 = RasPortEnum(0, v2, &dwBytes, &v17);
    if ( v4 != 603 )
      break;
    if ( v2 )
      HeapFree(hHeap, 0, v2);
    v2 = (char *)HeapAlloc(hHeap, 8u, (unsigned int)dwBytes);
    if ( !v2 )
    {
      dwErrorCode = GetLastError();
      v4 = dwErrorCode;
      if ( dword_1800C84E4 )
        RouterLogEventW(hLogHandle, 1u, 0x4E88u, 0, 0, dwErrorCode);
      break;
    }
    Sleep(100 * (100 - v3));
    v4 = 0;
    if ( !--v3 )
      goto LABEL_7;
  }
  if ( v4 )
  {
    if ( dword_1800C84E4 )
      RouterLogEventStringW(hLogHandle, 1u, 0x4E25u, 0, 0, v4, 0);
    goto LABEL_44;
  }
LABEL_7:
  v5 = 5;
  if ( v17 >= 5 )
  {
    v5 = v17;
    if ( v17 > 0x11 )
      v5 = 17;
  }
  if ( !DdmDeviceTable::GetInstance(v5) || !DdmConnectionTable::GetInstance() )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( dword_1800C84E4 )
      goto LABEL_43;
    goto LABEL_44;
  }
  v8 = 0;
  v9 = v2;
  if ( !v17 )
    goto LABEL_44;
  v10 = -1;
  while ( 1 )
  {
    if ( (v9[32] & 0x65) == 0 )
      goto LABEL_36;
    if ( *((_WORD *)v9 + 14) == 14 )
    {
      v11 = SetupSstpServerConfig();
      v4 = v11;
      if ( v11 )
      {
        if ( (byte_1800C8404 & 8) != 0 )
        {
          LOWORD(v26) = 0;
          FormatRRASErrorString(&v26, L"DDMServiceInitialize: SetupSstpServerConfig failed. Error %d", v11);
          if ( (byte_1800C8404 & 8) != 0 )
          {
            do
              ++v10;
            while ( *(_WORD *)&v27[2 * v10 - 4] );
            v23 = &v26;
            v24 = 2 * v10 + 2;
            v25 = 0;
            McGenEventWrite_EventWriteTransfer(
              &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              RasDdmTraceError,
              v15,
              2,
              WideCharStr);
          }
        }
        goto LABEL_44;
      }
    }
    v4 = RasPortOpen(v9 + 8, &v20, 0);
    plpszSubStringArray = 0;
    if ( v4 )
    {
      MultiByteToWideChar(0, 0, v9 + 8, -1, WideCharStr, 17);
      plpszSubStringArray = WideCharStr;
      if ( dword_1800C84E4 )
        RouterLogEventStringW(hLogHandle, 1u, 0x4E8Cu, 1u, &plpszSubStringArray, v4, 1u);
      v4 = 0;
      goto LABEL_36;
    }
    v12 = 0;
    if ( (v9[32] & 0x45) != 0 )
      break;
LABEL_33:
    if ( v12 && !_InterlockedDecrement((volatile signed __int32 *)v12 + 2) )
      (**(void (__fastcall ***)(LPWSTR, __int64))v12)(v12, 1);
LABEL_36:
    if ( ++v8 >= v17 )
      goto LABEL_44;
    v9 += 216;
  }
  DdmDeviceTable::GetInstance(0x11u);
  LastError = DdmDeviceTable::CreateNewDevice(v13, v20, v9, &plpszSubStringArray);
  v4 = LastError;
  v12 = plpszSubStringArray;
  if ( plpszSubStringArray )
  {
    Instance = DdmDeviceTable::GetInstance(0x11u);
    DdmDeviceTable::AddDevice(Instance);
    EnterCriticalSection((LPCRITICAL_SECTION)(v12 + 8));
    if ( (*((_DWORD *)v12 + 34) & 0xFFFF0000) != 0x20000 )
      *v21 = 1;
    LeaveCriticalSection((LPCRITICAL_SECTION)(v12 + 8));
    goto LABEL_33;
  }
  if ( !dword_1800C84E4 )
    goto LABEL_44;
LABEL_43:
  RouterLogEventW(hLogHandle, 1u, 0x4E88u, 0, 0, LastError);
LABEL_44:
  if ( v2 )
    HeapFree(hHeap, 0, v2);
  return v4;
}

```

## disassembly

```asm
0x1800157cc  push    rbp
0x1800157ce  push    rbx
0x1800157cf  push    rsi
0x1800157d0  push    rdi
0x1800157d1  push    r12
0x1800157d3  push    r13
0x1800157d5  push    r14
0x1800157d7  push    r15
0x1800157d9  lea     rbp, [rsp-7A8h]
0x1800157e1  sub     rsp, 8A8h
0x1800157e8  mov     rax, cs:__security_cookie
0x1800157ef  xor     rax, rsp
0x1800157f2  mov     [rbp+7E0h+var_50], rax
0x1800157f9  mov     rbx, rcx
0x1800157fc  mov     [rsp+8E0h+var_880], rcx
0x180015801  xor     r13d, r13d
0x180015804  mov     [rsp+8E0h+var_888], r13
0x180015809  mov     r14d, r13d
0x18001580c  mov     dword ptr [rsp+8E0h+dwBytes], r13d
0x180015811  mov     [rsp+8E0h+var_8A0], r13d
0x180015816  lea     r15d, [r13+64h]
0x18001581a  mov     edi, r15d
0x18001581d  mov     [rbp+7E0h+var_850], r13d
0x180015821  xor     edx, edx; Val
0x180015823  mov     r8d, 7FCh; Size
0x180015829  lea     rcx, [rbp+7E0h+var_84C]; void *
0x18001582d  call    memset_0
0x180015832  mov     [rbx], r13d
0x180015835  lea     r9, [rsp+8E0h+var_8A0]
0x18001583a  lea     r8, [rsp+8E0h+dwBytes]
0x18001583f  mov     rdx, r14
0x180015842  xor     ecx, ecx
0x180015844  call    cs:__imp_RasPortEnum
0x18001584a  mov     ebx, eax
0x18001584c  mov     esi, 1
0x180015851  mov     r12d, 4E88h
0x180015857  cmp     eax, 25Bh
0x18001585c  jnz     loc_18001593A
0x180015862  test    r14, r14
0x180015865  jz      short loc_180015879
0x180015867  mov     r8, r14; lpMem
0x18001586a  xor     edx, edx; dwFlags
0x18001586c  mov     rcx, cs:hHeap; hHeap
0x180015873  call    cs:__imp_HeapFree
0x180015879  mov     r8d, dword ptr [rsp+8E0h+dwBytes]; dwBytes
0x18001587e  mov     edx, 8; dwFlags
0x180015883  mov     rcx, cs:hHeap; hHeap
0x18001588a  call    cs:__imp_HeapAlloc
0x180015890  mov     r14, rax
0x180015893  test    rax, rax
0x180015896  jz      short loc_18001590B
0x180015898  mov     eax, r15d
0x18001589b  sub     eax, edi
0x18001589d  imul    ecx, eax, 64h ; 'd'; dwMilliseconds
0x1800158a0  call    cs:__imp_Sleep
0x1800158a6  mov     ebx, r13d
0x1800158a9  add     edi, 0FFFFFFFFh
0x1800158ac  jnz     short loc_180015835
0x1800158ae  mov     edx, 11h
0x1800158b3  mov     eax, [rsp+8E0h+var_8A0]
0x1800158b7  lea     ecx, [rdx-0Ch]
0x1800158ba  cmp     eax, ecx
0x1800158bc  jb      short loc_1800158C5
0x1800158be  mov     ecx, eax
0x1800158c0  cmp     eax, edx
0x1800158c2  cmova   ecx, edx; unsigned int
0x1800158c5  call    ?GetInstance@DdmDeviceTable@@SAPEAV1@K@Z; DdmDeviceTable::GetInstance(ulong)
0x1800158ca  test    rax, rax
0x1800158cd  jnz     loc_18001597A
0x1800158d3  call    cs:__imp_GetLastError
0x1800158d9  mov     ebx, eax
0x1800158db  cmp     cs:dword_1800C84E4, r13d
0x1800158e2  jbe     loc_180015BB2
0x1800158e8  mov     [rsp+8E0h+dwErrorCode], eax; dwErrorCode
0x1800158ec  mov     [rsp+8E0h+plpszSubStringArray], r13; plpszSubStringArray
0x1800158f1  xor     r9d, r9d; dwSubStringCount
0x1800158f4  mov     r8d, r12d; dwMessageId
0x1800158f7  mov     edx, esi; dwEventType
0x1800158f9  mov     rcx, cs:hLogHandle; hLogHandle
0x180015900  call    cs:__imp_RouterLogEventW
0x180015906  jmp     loc_180015BB2
0x18001590b  call    cs:__imp_GetLastError
0x180015911  mov     ebx, eax
0x180015913  cmp     cs:dword_1800C84E4, r13d
0x18001591a  jbe     short loc_18001593A
0x18001591c  mov     [rsp+8E0h+dwErrorCode], eax; dwErrorCode
0x180015920  mov     [rsp+8E0h+plpszSubStringArray], r13; plpszSubStringArray
0x180015925  xor     r9d, r9d; dwSubStringCount
0x180015928  mov     r8d, r12d; dwMessageId
0x18001592b  mov     edx, esi; dwEventType
0x18001592d  mov     rcx, cs:hLogHandle; hLogHandle
0x180015934  call    cs:__imp_RouterLogEventW
0x18001593a  test    ebx, ebx
0x18001593c  jz      loc_1800158AE
0x180015942  cmp     cs:dword_1800C84E4, r13d
0x180015949  jbe     loc_180015BB2
0x18001594f  mov     [rsp+8E0h+dwErrorIndex], r13d; dwErrorIndex
0x180015954  mov     [rsp+8E0h+dwErrorCode], ebx; dwErrorCode
0x180015958  mov     [rsp+8E0h+plpszSubStringArray], r13; plpszSubStringArray
0x18001595d  xor     r9d, r9d; dwSubStringCount
0x180015960  mov     r8d, 4E25h; dwMessageId
0x180015966  mov     edx, esi; dwEventType
0x180015968  mov     rcx, cs:hLogHandle; hLogHandle
0x18001596f  call    cs:__imp_RouterLogEventStringW
0x180015975  jmp     loc_180015BB2
0x18001597a  call    ?GetInstance@DdmConnectionTable@@SAPEAV1@XZ; DdmConnectionTable::GetInstance(void)
0x18001597f  test    rax, rax
0x180015982  jz      loc_1800158D3
0x180015988  mov     r12d, r13d
0x18001598b  mov     r15, r14
0x18001598e  cmp     [rsp+8E0h+var_8A0], r13d
0x180015993  jbe     loc_180015BB2
0x180015999  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18001599d  test    byte ptr [r15+20h], 65h
0x1800159a2  jz      loc_180015AF3
0x1800159a8  cmp     word ptr [r15+1Ch], 0Eh
0x1800159ae  jnz     short loc_1800159C0
0x1800159b0  call    cs:__imp_SetupSstpServerConfig
0x1800159b6  mov     ebx, eax
0x1800159b8  test    eax, eax
0x1800159ba  jnz     loc_180015B0D
0x1800159c0  xor     r8d, r8d
0x1800159c3  lea     rdx, [rsp+8E0h+var_888]
0x1800159c8  lea     rcx, [r15+8]
0x1800159cc  call    cs:__imp_RasPortOpen
0x1800159d2  mov     ebx, eax
0x1800159d4  mov     [rsp+8E0h+var_898], r13
0x1800159d9  test    eax, eax
0x1800159db  jz      short loc_180015A4A
0x1800159dd  mov     [rsp+8E0h+dwErrorCode], 11h; cchWideChar
0x1800159e5  lea     rax, [rsp+8E0h+WideCharStr]
0x1800159ea  mov     [rsp+8E0h+plpszSubStringArray], rax; lpWideCharStr
0x1800159ef  mov     r9d, esi; cbMultiByte
0x1800159f2  lea     r8, [r15+8]; lpMultiByteStr
0x1800159f6  xor     edx, edx; dwFlags
0x1800159f8  xor     ecx, ecx; CodePage
0x1800159fa  call    cs:__imp_MultiByteToWideChar
0x180015a00  lea     rax, [rsp+8E0h+WideCharStr]
0x180015a05  mov     [rsp+8E0h+var_898], rax
0x180015a0a  cmp     cs:dword_1800C84E4, r13d
0x180015a11  jbe     short loc_180015A42
0x180015a13  mov     ecx, 1
0x180015a18  mov     [rsp+8E0h+dwErrorIndex], ecx; dwErrorIndex
0x180015a1c  mov     [rsp+8E0h+dwErrorCode], ebx; dwErrorCode
0x180015a20  lea     rax, [rsp+8E0h+var_898]
0x180015a25  mov     [rsp+8E0h+plpszSubStringArray], rax; plpszSubStringArray
0x180015a2a  mov     r9d, ecx; dwSubStringCount
0x180015a2d  mov     r8d, 4E8Ch; dwMessageId
0x180015a33  mov     edx, ecx; dwEventType
0x180015a35  mov     rcx, cs:hLogHandle; hLogHandle
0x180015a3c  call    cs:__imp_RouterLogEventStringW
0x180015a42  mov     ebx, r13d
0x180015a45  jmp     loc_180015AF3
0x180015a4a  mov     rdi, r13
0x180015a4d  test    byte ptr [r15+20h], 45h
0x180015a52  jz      short loc_180015ACB
0x180015a54  mov     ecx, 11h; unsigned int
0x180015a59  call    ?GetInstance@DdmDeviceTable@@SAPEAV1@K@Z; DdmDeviceTable::GetInstance(ulong)
0x180015a5e  lea     r9, [rsp+8E0h+var_898]
0x180015a63  mov     r8, r15
0x180015a66  mov     rdx, [rsp+8E0h+var_888]
0x180015a6b  call    ?CreateNewDevice@DdmDeviceTable@@QEAAKPEAXPEAU_RASMAN_PORT@@AEAV?$RasObjPtr@VDdmDevice@@@@@Z; DdmDeviceTable::CreateNewDevice(void *,_RASMAN_PORT *,RasObjPtr<DdmDevice> &)
0x180015a70  mov     ebx, eax
0x180015a72  mov     rdi, [rsp+8E0h+var_898]
0x180015a77  test    rdi, rdi
0x180015a7a  jz      loc_180015B85
0x180015a80  mov     ecx, 11h; unsigned int
0x180015a85  call    ?GetInstance@DdmDeviceTable@@SAPEAV1@K@Z; DdmDeviceTable::GetInstance(ulong)
0x180015a8a  lea     rdx, [rsp+8E0h+var_898]
0x180015a8f  mov     rcx, rax; this
0x180015a92  call    ?AddDevice@DdmDeviceTable@@QEAAKAEAV?$RasObjPtr@VDdmDevice@@@@@Z; DdmDeviceTable::AddDevice(RasObjPtr<DdmDevice> &)
0x180015a97  lea     rcx, [rdi+10h]; lpCriticalSection
0x180015a9b  call    cs:__imp_EnterCriticalSection
0x180015aa1  mov     eax, [rdi+88h]
0x180015aa7  and     eax, 0FFFF0000h
0x180015aac  cmp     eax, 20000h
0x180015ab1  jz      short loc_180015ABE
0x180015ab3  mov     rax, [rsp+8E0h+var_880]
0x180015ab8  mov     dword ptr [rax], 1
0x180015abe  lea     rcx, [rdi+10h]; lpCriticalSection
0x180015ac2  call    cs:__imp_LeaveCriticalSection
0x180015ac8  xor     r13d, r13d
0x180015acb  test    rdi, rdi
0x180015ace  jz      short loc_180015AF3
0x180015ad0  mov     eax, esi
0x180015ad2  lock xadd [rdi+8], eax
0x180015ad7  add     eax, esi
0x180015ad9  jnz     short loc_180015AF3
0x180015adb  test    rdi, rdi
0x180015ade  jz      short loc_180015AF3
0x180015ae0  mov     rax, [rdi]
0x180015ae3  mov     edx, 1
0x180015ae8  mov     rcx, rdi
0x180015aeb  mov     rax, [rax]
0x180015aee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015af3  inc     r12d
0x180015af6  cmp     r12d, [rsp+8E0h+var_8A0]
0x180015afb  jnb     loc_180015BB2
0x180015b01  add     r15, 0D8h
0x180015b08  jmp     loc_18001599D
0x180015b0d  test    cs:byte_1800C8404, 8
0x180015b14  jz      loc_180015BB2
0x180015b1a  mov     word ptr [rbp+7E0h+var_850], r13w
0x180015b1f  mov     r8d, eax
0x180015b22  lea     rdx, aDdmserviceinit_21; "DDMServiceInitialize: SetupSstpServerCo"...
0x180015b29  lea     rcx, [rbp+7E0h+var_850]
0x180015b2d  call    FormatRRASErrorString
0x180015b32  test    cs:byte_1800C8404, 8
0x180015b39  jz      short loc_180015BB2
0x180015b3b  lea     rax, [rbp+7E0h+var_850]
0x180015b3f  inc     rsi
0x180015b42  cmp     [rax+rsi*2], r13w
0x180015b47  jnz     short loc_180015B3F
0x180015b49  lea     eax, ds:2[rsi*2]
0x180015b50  lea     rcx, [rbp+7E0h+var_850]
0x180015b54  mov     [rsp+8E0h+var_868], rcx
0x180015b59  mov     [rbp+7E0h+var_860], eax
0x180015b5c  mov     [rbp+7E0h+var_85C], r13d
0x180015b60  lea     rax, [rsp+8E0h+WideCharStr]
0x180015b65  mov     [rsp+8E0h+plpszSubStringArray], rax
0x180015b6a  mov     r9d, 2
0x180015b70  lea     rdx, RasDdmTraceError
0x180015b77  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180015b7e  call    McGenEventWrite_EventWriteTransfer
0x180015b83  jmp     short loc_180015BB2
0x180015b85  cmp     cs:dword_1800C84E4, r13d
0x180015b8c  jbe     short loc_180015BB2
0x180015b8e  mov     [rsp+8E0h+dwErrorCode], eax; dwErrorCode
0x180015b92  mov     [rsp+8E0h+plpszSubStringArray], r13; plpszSubStringArray
0x180015b97  xor     r9d, r9d; dwSubStringCount
0x180015b9a  lea     edx, [r9+1]; dwEventType
0x180015b9e  mov     r8d, 4E88h; dwMessageId
0x180015ba4  mov     rcx, cs:hLogHandle; hLogHandle
0x180015bab  call    cs:__imp_RouterLogEventW
0x180015bb1  nop
0x180015bb2  test    r14, r14
0x180015bb5  jz      short loc_180015BC9
0x180015bb7  mov     r8, r14; lpMem
0x180015bba  xor     edx, edx; dwFlags
0x180015bbc  mov     rcx, cs:hHeap; hHeap
0x180015bc3  call    cs:__imp_HeapFree
0x180015bc9  mov     eax, ebx
0x180015bcb  mov     rcx, [rbp+7E0h+var_50]
0x180015bd2  xor     rcx, rsp; StackCookie
0x180015bd5  call    __security_check_cookie
0x180015bda  add     rsp, 8A8h
0x180015be1  pop     r15
0x180015be3  pop     r14
0x180015be5  pop     r13
0x180015be7  pop     r12
0x180015be9  pop     rdi
0x180015bea  pop     rsi
0x180015beb  pop     rbx
0x180015bec  pop     rbp
0x180015bed  retn
```
