# CDataIntegrityScanTaskHandler::Pause(void)

- ea: `0x180004b10`
- end: `0x180004c61`
- name: `?Pause@CDataIntegrityScanTaskHandler@@UEAAJXZ`
- size: `337`
- prototype: `__int64 __fastcall(HANDLE *this)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1800032f8`
- `0x180004b10`
- `0x180006470`
- `0x180006498`
- `0x180006688`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180004bf5`
- `KERNEL32!GetLastError` at `0x180004bf5`
- `KERNEL32!SetEvent` at `0x180004beb`
- `KERNEL32!SetEvent` at `0x180004beb`

## string_xrefs

- `0x180004b22`: `CDataIntegrityScanTaskHandler::Pause`

## pseudocode

```c
__int64 __fastcall CDataIntegrityScanTaskHandler::Pause(HANDLE *this)
{
  _QWORD *ThreadLocalStoragePointer; // rax
  __int64 v3; // r8
  PVOID *v4; // rcx
  signed int LastError; // eax
  unsigned int v6; // ebx
  const char *v8; // [rsp+40h] [rbp-18h] BYREF
  unsigned int v9; // [rsp+48h] [rbp-10h]

  ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
  v8 = "CDataIntegrityScanTaskHandler::Pause";
  v3 = ThreadLocalStoragePointer[tls_index];
  *(_QWORD *)(v3 + 16) = "CDataIntegrityScanTaskHandler::Pause";
  ++*(_WORD *)(v3 + 8);
  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_aZs(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)"CDataIntegrityScanTaskHandler::Pause");
      v4 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 1) != 0 && *((_BYTE *)v4 + 25) >= 4u )
      WPP_SF_(v4[2], 35, &WPP_a6ebff40181d3a1f9fe9a55f66516085_Traceguids);
  }
  if ( SetEvent(this[11]) )
  {
    v9 = 0;
    v6 = 0;
  }
  else
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    v9 = v6;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_a6ebff40181d3a1f9fe9a55f66516085_Traceguids, v6);
    }
  }
  CHResultImp::~CHResultImp((CHResultImp *)&v8);
  return v6;
}

```

## disassembly

```asm
0x180004b10  mov     r11, rsp
0x180004b13  mov     [r11+8], rbx
0x180004b17  push    rsi
0x180004b18  sub     rsp, 50h
0x180004b1c  mov     edx, cs:_tls_index
0x180004b22  lea     r9, aCdataintegrity_3; "CDataIntegrityScanTaskHandler::Pause"
0x180004b29  mov     rax, gs:58h
0x180004b32  mov     rbx, rcx
0x180004b35  movzx   ecx, cs:?GlobalIndentString@@3U_STRING@@A; _STRING GlobalIndentString
0x180004b3c  mov     [r11-18h], r9
0x180004b40  mov     r8, [rax+rdx*8]
0x180004b44  mov     eax, 10h
0x180004b49  mov     edx, 8
0x180004b4e  mov     [rax+r8], r9
0x180004b52  movzx   eax, cx
0x180004b55  inc     word ptr [rdx+r8]
0x180004b5a  movzx   edx, word ptr [rdx+r8]
0x180004b5f  cmp     dx, cx
0x180004b62  cmovb   ax, dx
0x180004b66  cmovb   cx, dx
0x180004b6a  mov     [rsp+58h+var_28], ax
0x180004b6f  xor     eax, eax
0x180004b71  mov     [rsp+58h+var_24], eax
0x180004b75  mov     rax, cs:off_180047060; "                                       "...
0x180004b7c  mov     [rsp+58h+var_26], cx
0x180004b81  mov     [r11-20h], rax
0x180004b85  mov     rcx, cs:WPP_GLOBAL_Control
0x180004b8c  lea     rsi, WPP_GLOBAL_Control
0x180004b93  cmp     rcx, rsi
0x180004b96  jz      short loc_180004BE7
0x180004b98  test    byte ptr [rcx+1Ch], 1
0x180004b9c  jz      short loc_180004BC1
0x180004b9e  cmp     byte ptr [rcx+19h], 5
0x180004ba2  jb      short loc_180004BC1
0x180004ba4  mov     rcx, [rcx+10h]; LoggerHandle
0x180004ba8  mov     edx, 0Dh
0x180004bad  mov     [r11-38h], r9
0x180004bb1  lea     r9, [r11-28h]
0x180004bb5  call    WPP_SF_aZs
0x180004bba  mov     rcx, cs:WPP_GLOBAL_Control
0x180004bc1  cmp     rcx, rsi
0x180004bc4  jz      short loc_180004BE7
0x180004bc6  test    byte ptr [rcx+1Ch], 1
0x180004bca  jz      short loc_180004BE7
0x180004bcc  cmp     byte ptr [rcx+19h], 4
0x180004bd0  jb      short loc_180004BE7
0x180004bd2  mov     rcx, [rcx+10h]
0x180004bd6  lea     r8, WPP_a6ebff40181d3a1f9fe9a55f66516085_Traceguids
0x180004bdd  mov     edx, 23h ; '#'
0x180004be2  call    WPP_SF_
0x180004be7  mov     rcx, [rbx+58h]; hEvent
0x180004beb  call    cs:__imp_SetEvent
0x180004bf1  test    eax, eax
0x180004bf3  jnz     short loc_180004C40
0x180004bf5  call    cs:__imp_GetLastError
0x180004bfb  mov     ebx, eax
0x180004bfd  test    eax, eax
0x180004bff  jle     short loc_180004C0A
0x180004c01  movzx   ebx, ax
0x180004c04  or      ebx, 80070000h
0x180004c0a  mov     [rsp+58h+var_10], ebx
0x180004c0e  mov     rcx, cs:WPP_GLOBAL_Control
0x180004c15  cmp     rcx, rsi
0x180004c18  jz      short loc_180004C4A
0x180004c1a  test    byte ptr [rcx+1Ch], 1
0x180004c1e  jz      short loc_180004C4A
0x180004c20  cmp     byte ptr [rcx+19h], 2
0x180004c24  jb      short loc_180004C4A
0x180004c26  mov     rcx, [rcx+10h]
0x180004c2a  lea     r8, WPP_a6ebff40181d3a1f9fe9a55f66516085_Traceguids
0x180004c31  mov     edx, 24h ; '$'
0x180004c36  mov     r9d, ebx
0x180004c39  call    WPP_SF_d
0x180004c3e  jmp     short loc_180004C4A
0x180004c40  mov     [rsp+58h+var_10], 0
0x180004c48  xor     ebx, ebx
0x180004c4a  lea     rcx, [rsp+58h+var_18]; this
0x180004c4f  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x180004c54  mov     eax, ebx
0x180004c56  mov     rbx, [rsp+58h+arg_0]
0x180004c5b  add     rsp, 50h
0x180004c5f  pop     rsi
0x180004c60  retn
```
