# FastWppCallbackDnsapi

- ea: `0x1800af000`
- end: `0x1800af1ce`
- name: `FastWppCallbackDnsapi`
- size: `462`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x18008b5f0`
- `0x18008bf98`
- `0x1800af000`
- `0x1800c9c44`
- `0x1800c9e18`
- `0x1800d6aa8`
- `0x1800d6b18`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800af08b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800af08b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800af1a3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800af1a3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800af0e7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800af0e7`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800af079`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800af079`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x1800af04e`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x1800af04e`
- `api-ms-win-service-private-l1-1-0!I_QueryTagInformation` at `0x1800af156`
- `api-ms-win-service-private-l1-1-0!I_QueryTagInformation` at `0x1800af156`

## pseudocode

```c
HLOCAL FastWppCallbackDnsapi()
{
  const wchar_t *CommandLineW; // r12
  unsigned __int8 near **v1; // rbx
  signed int LastError; // eax
  char *v3; // r14
  unsigned int v4; // edx
  char v5; // r15
  __int64 v6; // rdx
  DWORD CurrentProcessId; // esi
  __int64 v8; // r8
  __int64 SubProcessTag; // rcx
  struct _TEB *v10; // rax
  unsigned int v11; // ebx
  wchar_t *v12; // rdi
  char v14[4]; // [rsp+60h] [rbp-A0h] BYREF
  int v15; // [rsp+6Ch] [rbp-94h]
  _QWORD v16[4]; // [rsp+70h] [rbp-90h] BYREF
  char pDestinationSid[80]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v18[80]; // [rsp+E0h] [rbp-20h] BYREF

  memset_0(v18, 0, 0x44u);
  *(_DWORD *)v14 = 0;
  memset_0(pDestinationSid, 0, 0x44u);
  v15 = 0;
  CommandLineW = GetCommandLineW();
  if ( InitOnceExecuteOnce(&g_ProcessUserSIDInitOnce, (PINIT_ONCE_FN)_ProcessUserSIDInitOnceCallback, 0, 0) )
  {
    LastError = 0;
    v1 = &g_rgbProcessUserSID;
  }
  else
  {
    v1 = 0;
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v15 = 137;
    if ( LastError >= 0 )
      LastError = -2147418113;
  }
  v3 = v18;
  if ( LastError >= 0 )
    v3 = (char *)v1;
  WxIsProcessAppContainer((int *)v14);
  v5 = v14[0];
  if ( *(_DWORD *)v14 )
    WxGetProcessAppContainerSID(pDestinationSid, v4);
  CurrentProcessId = GetCurrentProcessId();
  SubProcessTag = 0;
  v10 = NtCurrentTeb();
  if ( v10 )
    SubProcessTag = (__int64)v10->SubProcessTag;
  v11 = SubProcessTag;
  if ( SubProcessTag != (unsigned int)SubProcessTag && (BYTE1(xmmword_1801119E0) & 8) != 0 )
    WPP_SF_dI(SubProcessTag, v6, v8, CurrentProcessId, SubProcessTag);
  memset(v16, 0, 24);
  v12 = 0;
  if ( v11 )
  {
    v16[0] = __PAIR64__(v11, CurrentProcessId);
    I_QueryTagInformation(0, 1, v16);
    v12 = (wchar_t *)v16[2];
    v16[2] = 0;
  }
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    WPP_SF_dSl_sid__sid_dSd(SubProcessTag, v6, v8, CurrentProcessId, CommandLineW, v5, v3, pDestinationSid, v11, v12);
  return LocalFree(v12);
}

```

## disassembly

```asm
0x1800af000  push    rbp
0x1800af002  push    rbx
0x1800af003  push    rsi
0x1800af004  push    rdi
0x1800af005  push    r12
0x1800af007  push    r14
0x1800af009  push    r15
0x1800af00b  lea     rbp, [rsp-40h]
0x1800af010  sub     rsp, 140h
0x1800af017  mov     rax, cs:__security_cookie
0x1800af01e  xor     rax, rsp
0x1800af021  mov     [rbp+70h+var_40], rax
0x1800af025  mov     ebx, 44h ; 'D'
0x1800af02a  lea     rcx, [rbp+70h+var_90]; void *
0x1800af02e  mov     r8d, ebx; Size
0x1800af031  xor     edx, edx; Val
0x1800af033  call    memset_0
0x1800af038  mov     r8d, ebx; Size
0x1800af03b  mov     dword ptr [rsp+170h+var_110], 0
0x1800af043  xor     edx, edx; Val
0x1800af045  lea     rcx, [rbp+70h+pDestinationSid]; void *
0x1800af049  call    memset_0
0x1800af04e  call    cs:__imp_GetCommandLineW
0x1800af055  nop     dword ptr [rax+rax+00h]
0x1800af05a  xor     r9d, r9d; Context
0x1800af05d  mov     [rsp+170h+var_104], 0
0x1800af065  xor     r8d, r8d; Parameter
0x1800af068  lea     rdx, ?_ProcessUserSIDInitOnceCallback@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x1800af06f  lea     rcx, ?g_ProcessUserSIDInitOnce@@3T_RTL_RUN_ONCE@@A; InitOnce
0x1800af076  mov     r12, rax
0x1800af079  call    cs:__imp_InitOnceExecuteOnce
0x1800af080  nop     dword ptr [rax+rax+00h]
0x1800af085  test    eax, eax
0x1800af087  jnz     short loc_1800AF0B7
0x1800af089  xor     ebx, ebx
0x1800af08b  call    cs:__imp_GetLastError
0x1800af092  nop     dword ptr [rax+rax+00h]
0x1800af097  test    eax, eax
0x1800af099  jle     short loc_1800AF0A3
0x1800af09b  movzx   eax, ax
0x1800af09e  or      eax, 80070000h
0x1800af0a3  test    eax, eax
0x1800af0a5  mov     [rsp+170h+var_104], 89h
0x1800af0ad  mov     ecx, 8000FFFFh
0x1800af0b2  cmovns  eax, ecx
0x1800af0b5  jmp     short loc_1800AF0C0
0x1800af0b7  xor     eax, eax
0x1800af0b9  lea     rbx, ?g_rgbProcessUserSID@@3PAEA; uchar near * g_rgbProcessUserSID
0x1800af0c0  test    eax, eax
0x1800af0c2  lea     r14, [rbp+70h+var_90]
0x1800af0c6  lea     rcx, [rsp+170h+var_110]; int *
0x1800af0cb  cmovns  r14, rbx
0x1800af0cf  call    ?WxIsProcessAppContainer@@YAJPEAH@Z; WxIsProcessAppContainer(int *)
0x1800af0d4  mov     r15d, dword ptr [rsp+170h+var_110]
0x1800af0d9  test    r15d, r15d
0x1800af0dc  jz      short loc_1800AF0E7
0x1800af0de  lea     rcx, [rbp+70h+pDestinationSid]; pDestinationSid
0x1800af0e2  call    ?WxGetProcessAppContainerSID@@YAJPEAU_SID@@K@Z; WxGetProcessAppContainerSID(_SID *,ulong)
0x1800af0e7  call    cs:__imp_GetCurrentProcessId
0x1800af0ee  nop     dword ptr [rax+rax+00h]
0x1800af0f3  mov     esi, eax
0x1800af0f5  xor     ecx, ecx
0x1800af0f7  mov     rax, gs:30h
0x1800af100  test    rax, rax
0x1800af103  jz      short loc_1800AF10C
0x1800af105  mov     rcx, [rax+1720h]
0x1800af10c  mov     ebx, ecx
0x1800af10e  cmp     rcx, rbx
0x1800af111  jz      short loc_1800AF129
0x1800af113  test    byte ptr cs:xmmword_1801119E0+1, 8
0x1800af11a  jz      short loc_1800AF129
0x1800af11c  mov     r9d, esi
0x1800af11f  mov     [rsp+170h+var_150], rcx
0x1800af124  call    WPP_SF_dI
0x1800af129  xor     eax, eax
0x1800af12b  mov     [rsp+170h+var_100], 0
0x1800af133  xor     edi, edi
0x1800af135  mov     [rbp+70h+var_EC], eax
0x1800af138  xorps   xmm0, xmm0
0x1800af13b  movups  [rsp+170h+var_FC], xmm0
0x1800af140  test    ebx, ebx
0x1800af142  jz      short loc_1800AF16E
0x1800af144  lea     r8, [rsp+170h+var_100]
0x1800af149  mov     [rsp+170h+var_100], esi
0x1800af14d  lea     edx, [rax+1]
0x1800af150  mov     dword ptr [rsp+170h+var_FC], ebx
0x1800af154  xor     ecx, ecx
0x1800af156  call    cs:__imp_I_QueryTagInformation
0x1800af15d  nop     dword ptr [rax+rax+00h]
0x1800af162  mov     rdi, qword ptr [rbp+70h+var_FC+0Ch]
0x1800af166  mov     qword ptr [rbp+70h+var_FC+0Ch], 0
0x1800af16e  test    byte ptr cs:xmmword_1801119E0+1, 8
0x1800af175  jz      short loc_1800AF1A0
0x1800af177  mov     [rsp+170h+var_128], rdi; __int64
0x1800af17c  lea     rax, [rbp+70h+pDestinationSid]
0x1800af180  mov     dword ptr [rsp+170h+var_130], ebx; char
0x1800af184  mov     r9d, esi; int
0x1800af187  mov     [rsp+170h+pSid], rax; pSid
0x1800af18c  mov     [rsp+170h+var_140], r14; PSID
0x1800af191  mov     dword ptr [rsp+170h+var_148], r15d; char
0x1800af196  mov     [rsp+170h+var_150], r12; __int64
0x1800af19b  call    WPP_SF_dSl_sid__sid_dSd
0x1800af1a0  mov     rcx, rdi; hMem
0x1800af1a3  call    cs:__imp_LocalFree
0x1800af1aa  nop     dword ptr [rax+rax+00h]
0x1800af1af  mov     rcx, [rbp+70h+var_40]
0x1800af1b3  xor     rcx, rsp; StackCookie
0x1800af1b6  call    __security_check_cookie
0x1800af1bb  add     rsp, 140h
0x1800af1c2  pop     r15
0x1800af1c4  pop     r14
0x1800af1c6  pop     r12
0x1800af1c8  pop     rdi
0x1800af1c9  pop     rsi
0x1800af1ca  pop     rbx
0x1800af1cb  pop     rbp
0x1800af1cc  retn
```
