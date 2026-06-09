# InitializDeviceTable(void)

- ea: `0x1800157a0`
- end: `0x180015a6a`
- name: `?InitializDeviceTable@@YAKXZ`
- size: `714`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001bf40`

## callees

- `0x180007c0c`
- `0x180011880`
- `0x1800157a0`
- `0x180030684`
- `0x18003d278`
- `0x1800755b8`
- `0x180092a92`
- `0x180092ad0`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x1800158c5`
- `KERNEL32!HeapAlloc` at `0x1800158c5`
- `KERNEL32!GetLastError` at `0x1800159e7`
- `KERNEL32!GetLastError` at `0x1800159e7`
- `KERNEL32!HeapFree` at `0x180015a33`
- `KERNEL32!HeapFree` at `0x180015a33`
- `rtutils!RouterLogEventW` at `0x180015a1b`
- `rtutils!RouterLogEventW` at `0x180015a1b`

## string_xrefs

- `0x180015841`: `DDMServiceInitialize: DdmGetDeviceConfigInfo failed: Error %d`
- `0x180015961`: `DDMServiceInitialize: DdmGetDeviceConfigInfo failed: Error %d`
- `0x1800158f1`: `DDMServiceInitialize: Malloc failed: Error %d`

## pseudocode

```c
__int64 InitializDeviceTable(void)
{
  unsigned int DeviceConfigInfo; // eax
  unsigned int v1; // ebx
  __int64 v2; // r8
  __int64 v3; // rax
  void *v4; // rax
  void *v5; // rsi
  unsigned int v6; // eax
  __int64 v7; // r8
  __int64 v8; // rax
  DWORD dwErrorCode; // eax
  SIZE_T dwBytes; // [rsp+38h] [rbp-D0h] BYREF
  int v12; // [rsp+40h] [rbp-C8h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v13; // [rsp+48h] [rbp-C0h] BYREF
  int *v14; // [rsp+58h] [rbp-B0h]
  int v15; // [rsp+60h] [rbp-A8h]
  int v16; // [rsp+64h] [rbp-A4h]
  int v17; // [rsp+68h] [rbp-A0h] BYREF
  _BYTE v18[2044]; // [rsp+6Ch] [rbp-9Ch] BYREF

  v12 = 6;
  dwBytes = 0;
  v17 = 0;
  memset_0(v18, 0, sizeof(v18));
  DeviceConfigInfo = DdmGetDeviceConfigInfo(0, (int)&v12, (int)&dwBytes + 4, (int)&dwBytes, 0);
  v1 = DeviceConfigInfo;
  if ( !DeviceConfigInfo || DeviceConfigInfo == 603 )
  {
    v4 = HeapAlloc(hHeap, 8u, (unsigned int)dwBytes);
    v5 = v4;
    if ( v4 )
    {
      v6 = DdmGetDeviceConfigInfo(0, (int)&v12, (int)&dwBytes + 4, (int)&dwBytes, v4);
      v1 = v6;
      if ( v6 )
      {
        if ( (byte_1800CF404 & 8) != 0 )
        {
          LOWORD(v17) = 0;
          FormatRRASErrorString(&v17, L"DDMServiceInitialize: DdmGetDeviceConfigInfo failed: Error %d", v6);
          if ( (byte_1800CF404 & 8) != 0 )
          {
            v8 = -1;
            do
              ++v8;
            while ( *(_WORD *)&v18[2 * v8 - 4] );
            v16 = 0;
            v15 = 2 * v8 + 2;
            v14 = &v17;
            McGenEventWrite_EventWriteTransfer(
              (REGHANDLE *)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (const EVENT_DESCRIPTOR *)RasDdmTraceError,
              v7,
              2u,
              &v13);
          }
        }
      }
      else if ( !DdmDeviceTable::GetInstance(0) || !DdmConnectionTable::GetInstance() )
      {
        dwErrorCode = GetLastError();
        v1 = dwErrorCode;
        if ( dword_1800CF4E4 )
          RouterLogEventW(hLogHandle, 1u, 0x4E88u, 0, 0, dwErrorCode);
      }
      HeapFree(hHeap, 0, v5);
    }
    else
    {
      v1 = 8;
      if ( (byte_1800CF404 & 8) != 0 )
      {
        LOWORD(v17) = 0;
        FormatRRASErrorString(&v17, L"DDMServiceInitialize: Malloc failed: Error %d", 8);
        if ( (byte_1800CF404 & 8) != 0 )
        {
          v3 = -1;
          do
            ++v3;
          while ( *(_WORD *)&v18[2 * v3 - 4] );
          goto LABEL_7;
        }
      }
    }
  }
  else if ( (byte_1800CF404 & 8) != 0 )
  {
    LOWORD(v17) = 0;
    FormatRRASErrorString(&v17, L"DDMServiceInitialize: DdmGetDeviceConfigInfo failed: Error %d", DeviceConfigInfo);
    if ( (byte_1800CF404 & 8) != 0 )
    {
      v3 = -1;
      do
        ++v3;
      while ( *(_WORD *)&v18[2 * v3 - 4] );
LABEL_7:
      v16 = 0;
      v15 = 2 * v3 + 2;
      v14 = &v17;
      McGenEventWrite_EventWriteTransfer(
        (REGHANDLE *)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (const EVENT_DESCRIPTOR *)RasDdmTraceError,
        v2,
        2u,
        &v13);
    }
  }
  return v1;
}

```

## disassembly

```asm
0x1800157a0  mov     rax, rsp
0x1800157a3  mov     [rax+8], rbx
0x1800157a7  mov     [rax+10h], rsi
0x1800157ab  mov     [rax+18h], r14
0x1800157af  push    rbp
0x1800157b0  lea     rbp, [rax-778h]
0x1800157b7  sub     rsp, 870h
0x1800157be  mov     rax, cs:__security_cookie
0x1800157c5  xor     rax, rsp
0x1800157c8  mov     [rbp+770h+var_10], rax
0x1800157cf  xor     r14d, r14d
0x1800157d2  mov     [rsp+870h+var_838], 6
0x1800157da  xor     edx, edx; Val
0x1800157dc  mov     dword ptr [rsp+870h+dwBytes+4], r14d
0x1800157e1  mov     r8d, 7FCh; Size
0x1800157e7  mov     dword ptr [rsp+870h+dwBytes], r14d
0x1800157ec  lea     rcx, [rsp+870h+var_80C]; void *
0x1800157f1  mov     [rsp+870h+var_810], r14d
0x1800157f6  call    memset_0
0x1800157fb  lea     r9, [rsp+870h+dwBytes]; int
0x180015800  mov     [rsp+870h+plpszSubStringArray], r14; void *
0x180015805  lea     r8, [rsp+870h+dwBytes+4]; int
0x18001580a  xor     ecx, ecx; int
0x18001580c  lea     rdx, [rsp+870h+var_838]; int
0x180015811  call    DdmGetDeviceConfigInfo
0x180015816  mov     ebx, eax
0x180015818  test    eax, eax
0x18001581a  jz      loc_1800158B4
0x180015820  cmp     eax, 25Bh
0x180015825  jz      loc_1800158B4
0x18001582b  test    cs:byte_1800CF404, 8
0x180015832  jz      loc_180015A3F
0x180015838  mov     r8d, eax
0x18001583b  mov     word ptr [rsp+870h+var_810], r14w
0x180015841  lea     rdx, aDdmserviceinit_32; "DDMServiceInitialize: DdmGetDeviceConfi"...
0x180015848  lea     rcx, [rsp+870h+var_810]
0x18001584d  call    FormatRRASErrorString
0x180015852  test    cs:byte_1800CF404, 8
0x180015859  jz      loc_180015A3F
0x18001585f  lea     rcx, [rsp+870h+var_810]
0x180015864  or      rax, 0FFFFFFFFFFFFFFFFh
0x180015868  inc     rax
0x18001586b  cmp     [rcx+rax*2], r14w
0x180015870  jnz     short loc_180015868
0x180015872  lea     eax, ds:2[rax*2]
0x180015879  mov     [rsp+870h+var_814], r14d
0x18001587e  lea     rcx, [rsp+870h+var_810]
0x180015883  mov     [rsp+870h+var_818], eax
0x180015887  lea     rax, [rsp+870h+var_830]
0x18001588c  mov     [rsp+870h+var_820], rcx
0x180015891  mov     r9d, 2
0x180015897  mov     [rsp+870h+plpszSubStringArray], rax
0x18001589c  lea     rdx, RasDdmTraceError
0x1800158a3  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800158aa  call    McGenEventWrite_EventWriteTransfer
0x1800158af  jmp     loc_180015A3F
0x1800158b4  mov     r8d, dword ptr [rsp+870h+dwBytes]; dwBytes
0x1800158b9  mov     edx, 8; dwFlags
0x1800158be  mov     rcx, cs:hHeap; hHeap
0x1800158c5  call    cs:__imp_HeapAlloc
0x1800158cc  nop     dword ptr [rax+rax+00h]
0x1800158d1  mov     rsi, rax
0x1800158d4  test    rax, rax
0x1800158d7  jnz     short loc_180015926
0x1800158d9  lea     ebx, [rax+8]
0x1800158dc  test    cs:byte_1800CF404, bl
0x1800158e2  jz      loc_180015A3F
0x1800158e8  mov     r8d, ebx
0x1800158eb  mov     word ptr [rsp+870h+var_810], r14w
0x1800158f1  lea     rdx, aDdmserviceinit_8; "DDMServiceInitialize: Malloc failed: Er"...
0x1800158f8  lea     rcx, [rsp+870h+var_810]
0x1800158fd  call    FormatRRASErrorString
0x180015902  test    cs:byte_1800CF404, bl
0x180015908  jz      loc_180015A3F
0x18001590e  lea     rcx, [rsp+870h+var_810]
0x180015913  or      rax, 0FFFFFFFFFFFFFFFFh
0x180015917  inc     rax
0x18001591a  cmp     [rcx+rax*2], r14w
0x18001591f  jnz     short loc_180015917
0x180015921  jmp     loc_180015872
0x180015926  lea     r9, [rsp+870h+dwBytes]; int
0x18001592b  mov     [rsp+870h+plpszSubStringArray], rsi; void *
0x180015930  lea     r8, [rsp+870h+dwBytes+4]; int
0x180015935  xor     ecx, ecx; int
0x180015937  lea     rdx, [rsp+870h+var_838]; int
0x18001593c  call    DdmGetDeviceConfigInfo
0x180015941  mov     ebx, eax
0x180015943  test    eax, eax
0x180015945  jz      loc_1800159D1
0x18001594b  test    cs:byte_1800CF404, 8
0x180015952  jz      loc_180015A27
0x180015958  mov     r8d, eax
0x18001595b  mov     word ptr [rsp+870h+var_810], r14w
0x180015961  lea     rdx, aDdmserviceinit_32; "DDMServiceInitialize: DdmGetDeviceConfi"...
0x180015968  lea     rcx, [rsp+870h+var_810]
0x18001596d  call    FormatRRASErrorString
0x180015972  test    cs:byte_1800CF404, 8
0x180015979  jz      loc_180015A27
0x18001597f  lea     rcx, [rsp+870h+var_810]
0x180015984  or      rax, 0FFFFFFFFFFFFFFFFh
0x180015988  inc     rax
0x18001598b  cmp     [rcx+rax*2], r14w
0x180015990  jnz     short loc_180015988
0x180015992  lea     eax, ds:2[rax*2]
0x180015999  mov     [rsp+870h+var_814], r14d
0x18001599e  lea     rcx, [rsp+870h+var_810]
0x1800159a3  mov     [rsp+870h+var_818], eax
0x1800159a7  lea     rax, [rsp+870h+var_830]
0x1800159ac  mov     [rsp+870h+var_820], rcx
0x1800159b1  mov     r9d, 2
0x1800159b7  mov     [rsp+870h+plpszSubStringArray], rax
0x1800159bc  lea     rdx, RasDdmTraceError
0x1800159c3  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800159ca  call    McGenEventWrite_EventWriteTransfer
0x1800159cf  jmp     short loc_180015A27
0x1800159d1  xor     ecx, ecx; unsigned int
0x1800159d3  call    ?GetInstance@DdmDeviceTable@@SAPEAV1@K@Z; DdmDeviceTable::GetInstance(ulong)
0x1800159d8  test    rax, rax
0x1800159db  jz      short loc_1800159E7
0x1800159dd  call    ?GetInstance@DdmConnectionTable@@SAPEAV1@XZ; DdmConnectionTable::GetInstance(void)
0x1800159e2  test    rax, rax
0x1800159e5  jnz     short loc_180015A27
0x1800159e7  call    cs:__imp_GetLastError
0x1800159ee  nop     dword ptr [rax+rax+00h]
0x1800159f3  cmp     cs:dword_1800CF4E4, r14d
0x1800159fa  mov     ebx, eax
0x1800159fc  jbe     short loc_180015A27
0x1800159fe  mov     rcx, cs:hLogHandle; hLogHandle
0x180015a05  xor     r9d, r9d; dwSubStringCount
0x180015a08  mov     [rsp+870h+dwErrorCode], eax; dwErrorCode
0x180015a0c  mov     r8d, 4E88h; dwMessageId
0x180015a12  mov     [rsp+870h+plpszSubStringArray], r14; plpszSubStringArray
0x180015a17  lea     edx, [r9+1]; dwEventType
0x180015a1b  call    cs:__imp_RouterLogEventW
0x180015a22  nop     dword ptr [rax+rax+00h]
0x180015a27  mov     rcx, cs:hHeap; hHeap
0x180015a2e  mov     r8, rsi; lpMem
0x180015a31  xor     edx, edx; dwFlags
0x180015a33  call    cs:__imp_HeapFree
0x180015a3a  nop     dword ptr [rax+rax+00h]
0x180015a3f  mov     eax, ebx
0x180015a41  mov     rcx, [rbp+770h+var_10]
0x180015a48  xor     rcx, rsp; StackCookie
0x180015a4b  call    __security_check_cookie
0x180015a50  lea     r11, [rsp+870h+var_s0]
0x180015a58  mov     rbx, [r11+10h]
0x180015a5c  mov     rsi, [r11+18h]
0x180015a60  mov     r14, [r11+20h]
0x180015a64  mov     rsp, r11
0x180015a67  pop     rbp
0x180015a68  retn
```
