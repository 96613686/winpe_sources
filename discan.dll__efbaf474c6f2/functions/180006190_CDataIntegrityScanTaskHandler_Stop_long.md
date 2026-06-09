# CDataIntegrityScanTaskHandler::Stop(long *)

- ea: `0x180006190`
- end: `0x18000635d`
- name: `?Stop@CDataIntegrityScanTaskHandler@@UEAAJPEAJ@Z`
- size: `461`
- prototype: `__int64 __fastcall(CDataIntegrityScanTaskHandler *__hidden this, int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1800032f8`
- `0x180006190`
- `0x180006470`
- `0x180006498`
- `0x180006688`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000627d`
- `KERNEL32!GetLastError` at `0x18000627d`
- `KERNEL32!SetEvent` at `0x180006273`
- `KERNEL32!SetEvent` at `0x180006273`
- `KERNEL32!WaitForSingleObject` at `0x1800062fe`
- `KERNEL32!WaitForSingleObject` at `0x1800062fe`

## string_xrefs

- `0x1800061c6`: `CDataIntegrityScanTaskHandler::Stop`

## pseudocode

```c
__int64 __fastcall CDataIntegrityScanTaskHandler::Stop(HANDLE *this, unsigned int *a2)
{
  __int64 v4; // r9
  PVOID *v5; // rcx
  signed int LastError; // eax
  unsigned int v7; // ebx
  const char *v9; // [rsp+40h] [rbp-18h] BYREF
  unsigned int v10; // [rsp+48h] [rbp-10h]

  v4 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  v9 = "CDataIntegrityScanTaskHandler::Stop";
  ++*(_WORD *)(v4 + 8);
  *(_QWORD *)(v4 + 16) = "CDataIntegrityScanTaskHandler::Stop";
  v5 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_aZs(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)"CDataIntegrityScanTaskHandler::Stop");
      v5 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 1) != 0 && *((_BYTE *)v5 + 25) >= 4u )
      WPP_SF_(v5[2], 31, &WPP_a6ebff40181d3a1f9fe9a55f66516085_Traceguids);
  }
  if ( SetEvent(this[9]) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, &WPP_a6ebff40181d3a1f9fe9a55f66516085_Traceguids);
    }
    WaitForSingleObject(this[13], 0xFFFFFFFF);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, &WPP_a6ebff40181d3a1f9fe9a55f66516085_Traceguids);
    }
    *a2 = 0;
    v7 = 0;
    v10 = 0;
  }
  else
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    v10 = v7;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_a6ebff40181d3a1f9fe9a55f66516085_Traceguids, v7);
    }
    *a2 = v7;
  }
  CHResultImp::~CHResultImp((CHResultImp *)&v9);
  return v7;
}

```

## disassembly

```asm
0x180006190  mov     r11, rsp
0x180006193  mov     [r11+8], rbx
0x180006197  mov     [r11+10h], rbp
0x18000619b  push    rdi
0x18000619c  sub     rsp, 50h
0x1800061a0  mov     r8d, cs:_tls_index
0x1800061a7  mov     rdi, rdx
0x1800061aa  mov     rax, gs:58h
0x1800061b3  mov     rbx, rcx
0x1800061b6  movzx   ecx, cs:?GlobalIndentString@@3U_STRING@@A; _STRING GlobalIndentString
0x1800061bd  mov     edx, 8
0x1800061c2  mov     r9, [rax+r8*8]
0x1800061c6  lea     r8, aCdataintegrity_0; "CDataIntegrityScanTaskHandler::Stop"
0x1800061cd  mov     eax, 10h
0x1800061d2  mov     [r11-18h], r8
0x1800061d6  inc     word ptr [rdx+r9]
0x1800061db  movzx   edx, word ptr [rdx+r9]
0x1800061e0  mov     [rax+r9], r8
0x1800061e4  cmp     dx, cx
0x1800061e7  movzx   eax, cx
0x1800061ea  cmovb   ax, dx
0x1800061ee  cmovb   cx, dx
0x1800061f2  mov     [rsp+58h+var_28], ax
0x1800061f7  xor     eax, eax
0x1800061f9  mov     [rsp+58h+var_24], eax
0x1800061fd  mov     rax, cs:off_180047060; "                                       "...
0x180006204  mov     [rsp+58h+var_26], cx
0x180006209  mov     [r11-20h], rax
0x18000620d  mov     rcx, cs:WPP_GLOBAL_Control
0x180006214  lea     rbp, WPP_GLOBAL_Control
0x18000621b  cmp     rcx, rbp
0x18000621e  jz      short loc_18000626F
0x180006220  test    byte ptr [rcx+1Ch], 1
0x180006224  jz      short loc_180006249
0x180006226  cmp     byte ptr [rcx+19h], 5
0x18000622a  jb      short loc_180006249
0x18000622c  mov     rcx, [rcx+10h]; LoggerHandle
0x180006230  lea     r9, [r11-28h]
0x180006234  mov     edx, 0Dh
0x180006239  mov     [r11-38h], r8
0x18000623d  call    WPP_SF_aZs
0x180006242  mov     rcx, cs:WPP_GLOBAL_Control
0x180006249  cmp     rcx, rbp
0x18000624c  jz      short loc_18000626F
0x18000624e  test    byte ptr [rcx+1Ch], 1
0x180006252  jz      short loc_18000626F
0x180006254  cmp     byte ptr [rcx+19h], 4
0x180006258  jb      short loc_18000626F
0x18000625a  mov     rcx, [rcx+10h]
0x18000625e  lea     r8, WPP_a6ebff40181d3a1f9fe9a55f66516085_Traceguids
0x180006265  mov     edx, 1Fh
0x18000626a  call    WPP_SF_
0x18000626f  mov     rcx, [rbx+48h]; hEvent
0x180006273  call    cs:__imp_SetEvent
0x180006279  test    eax, eax
0x18000627b  jnz     short loc_1800062CA
0x18000627d  call    cs:__imp_GetLastError
0x180006283  mov     ebx, eax
0x180006285  test    eax, eax
0x180006287  jle     short loc_180006292
0x180006289  movzx   ebx, ax
0x18000628c  or      ebx, 80070000h
0x180006292  mov     [rsp+58h+var_10], ebx
0x180006296  mov     rcx, cs:WPP_GLOBAL_Control
0x18000629d  cmp     rcx, rbp
0x1800062a0  jz      short loc_1800062C6
0x1800062a2  test    byte ptr [rcx+1Ch], 1
0x1800062a6  jz      short loc_1800062C6
0x1800062a8  cmp     byte ptr [rcx+19h], 2
0x1800062ac  jb      short loc_1800062C6
0x1800062ae  mov     rcx, [rcx+10h]
0x1800062b2  lea     r8, WPP_a6ebff40181d3a1f9fe9a55f66516085_Traceguids
0x1800062b9  mov     edx, 20h ; ' '
0x1800062be  mov     r9d, ebx
0x1800062c1  call    WPP_SF_d
0x1800062c6  mov     [rdi], ebx
0x1800062c8  jmp     short loc_180006341
0x1800062ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1800062d1  cmp     rcx, rbp
0x1800062d4  jz      short loc_1800062F7
0x1800062d6  test    byte ptr [rcx+1Ch], 1
0x1800062da  jz      short loc_1800062F7
0x1800062dc  cmp     byte ptr [rcx+19h], 4
0x1800062e0  jb      short loc_1800062F7
0x1800062e2  mov     rcx, [rcx+10h]
0x1800062e6  lea     r8, WPP_a6ebff40181d3a1f9fe9a55f66516085_Traceguids
0x1800062ed  mov     edx, 21h ; '!'
0x1800062f2  call    WPP_SF_
0x1800062f7  mov     rcx, [rbx+68h]; hHandle
0x1800062fb  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800062fe  call    cs:__imp_WaitForSingleObject
0x180006304  mov     rcx, cs:WPP_GLOBAL_Control
0x18000630b  cmp     rcx, rbp
0x18000630e  jz      short loc_180006331
0x180006310  test    byte ptr [rcx+1Ch], 1
0x180006314  jz      short loc_180006331
0x180006316  cmp     byte ptr [rcx+19h], 4
0x18000631a  jb      short loc_180006331
0x18000631c  mov     rcx, [rcx+10h]
0x180006320  lea     r8, WPP_a6ebff40181d3a1f9fe9a55f66516085_Traceguids
0x180006327  mov     edx, 22h ; '"'
0x18000632c  call    WPP_SF_
0x180006331  mov     dword ptr [rdi], 0
0x180006337  xor     ebx, ebx
0x180006339  mov     [rsp+58h+var_10], 0
0x180006341  lea     rcx, [rsp+58h+var_18]; this
0x180006346  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x18000634b  mov     rbp, [rsp+58h+arg_8]
0x180006350  mov     eax, ebx
0x180006352  mov     rbx, [rsp+58h+arg_0]
0x180006357  add     rsp, 50h
0x18000635b  pop     rdi
0x18000635c  retn
```
