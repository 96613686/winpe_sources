# VistaBltTelemetryReport(VistaBltReason)

- ea: `0x180004300`
- end: `0x18000458e`
- name: `?VistaBltTelemetryReport@@YAXW4VistaBltReason@@@Z`
- size: `654`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180002200`

## callees

- `0x180003370`
- `0x180004300`
- `0x18000d0a0`
- `0x18000ddc4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800043ad`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800043ad`
- `ntdll!EtwEventWriteTransfer` at `0x180004553`
- `ntdll!EtwEventWriteTransfer` at `0x180004553`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180004368`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180004368`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004564`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004564`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004334`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004334`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004399`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004399`

## pseudocode

```c
void __fastcall VistaBltTelemetryReport(unsigned int a1)
{
  __int64 v1; // rbx
  wchar_t *v2; // rax
  WCHAR *v3; // rax
  __int64 v4; // rcx
  _WORD *v5; // r9
  __int64 v6; // r8
  _WORD *v7; // rdx
  int v8; // ecx
  __int64 v9; // rax
  _DWORD v11[2]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v12; // [rsp+38h] [rbp-C8h] BYREF
  _DWORD v13[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v14; // [rsp+48h] [rbp-B8h]
  __int16 *v15; // [rsp+50h] [rbp-B0h] BYREF
  int v16; // [rsp+58h] [rbp-A8h]
  int v17; // [rsp+5Ch] [rbp-A4h]
  char *v18; // [rsp+60h] [rbp-A0h]
  int v19; // [rsp+68h] [rbp-98h]
  int v20; // [rsp+6Ch] [rbp-94h]
  __int64 *v21; // [rsp+70h] [rbp-90h]
  __int64 v22; // [rsp+78h] [rbp-88h]
  _OWORD *v23; // [rsp+80h] [rbp-80h]
  int v24; // [rsp+88h] [rbp-78h]
  int v25; // [rsp+8Ch] [rbp-74h]
  _DWORD *v26; // [rsp+90h] [rbp-70h]
  __int64 v27; // [rsp+98h] [rbp-68h]
  _OWORD v28[8]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR Filename[264]; // [rsp+120h] [rbp+20h] BYREF

  v1 = a1;
  EnterCriticalSection(&CDwmHwndData::s_cs);
  if ( !*((_BYTE *)qword_18001F950 + v1) )
  {
    memset_0(Filename, 0, 0x208u);
    if ( GetModuleFileNameW(0, Filename, 0x104u) )
    {
      memset(v28, 0, sizeof(v28));
      if ( GetLastError() == 122 )
      {
        v3 = (WCHAR *)&qword_18001A0D0;
      }
      else
      {
        v2 = wcsrchr(Filename, 0x5Cu);
        if ( v2 )
          v3 = v2 + 1;
        else
          v3 = Filename;
      }
      v4 = 2147483646;
      v5 = v28;
      v6 = 64;
      do
      {
        if ( !v4 )
          break;
        if ( !*v3 )
          break;
        *v5++ = *v3++;
        --v4;
        --v6;
      }
      while ( v6 );
      v7 = v5 - 1;
      v8 = -2147024774;
      if ( v6 )
      {
        v7 = v5;
        v8 = 0;
      }
      *v7 = 0;
      if ( !v6 )
        DoStackCaptureDirect(v8, 0x212u);
      if ( (unsigned int)dword_18001F268 > 5
        && (qword_18001F278 & 0x400000000000LL) != 0
        && (qword_18001F280 & 0x400000000000LL) == qword_18001F280 )
      {
        v11[0] = v1;
        v26 = v11;
        v9 = -1;
        v12 = 0x1000000;
        v27 = 4;
        while ( *((_WORD *)v28 + ++v9) != 0 )
          ;
        v14 = 0x400000000000LL;
        v24 = 2 * v9 + 2;
        v23 = v28;
        v21 = &v12;
        v13[1] = 5;
        v15 = (__int16 *)off_18001F270;
        v25 = 0;
        v22 = 8;
        v13[0] = 184549376;
        v16 = *(unsigned __int16 *)off_18001F270;
        v18 = byte_18001ADFD;
        v17 = 2;
        v19 = 60;
        v20 = 1;
        v11[1] = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
        EtwEventWriteTransfer(qword_18001F288, v13, 0, 0, 5, &v15);
      }
    }
  }
  *((_BYTE *)qword_18001F950 + v1) = 1;
  LeaveCriticalSection(&CDwmHwndData::s_cs);
}

```

## disassembly

```asm
0x180004300  mov     [rsp-8+arg_8], rbx
0x180004305  mov     [rsp-8+arg_10], rdi
0x18000430a  push    rbp
0x18000430b  lea     rbp, [rsp-240h]
0x180004313  sub     rsp, 340h
0x18000431a  mov     rax, cs:__security_cookie
0x180004321  xor     rax, rsp
0x180004324  mov     [rbp+240h+var_10], rax
0x18000432b  mov     ebx, ecx
0x18000432d  lea     rcx, ?s_cs@CDwmHwndData@@0VCDwmCS@@A; lpCriticalSection
0x180004334  call    cs:__imp_EnterCriticalSection
0x18000433a  lea     rdi, qword_18001F950
0x180004341  cmp     byte ptr [rdi+rbx], 0
0x180004345  jnz     loc_180004559
0x18000434b  xor     edx, edx; Val
0x18000434d  lea     rcx, [rbp+240h+Filename]; void *
0x180004351  mov     r8d, 208h; Size
0x180004357  call    memset_0
0x18000435c  mov     r8d, 104h; nSize
0x180004362  lea     rdx, [rbp+240h+Filename]; lpFilename
0x180004366  xor     ecx, ecx; hModule
0x180004368  call    cs:__imp_GetModuleFileNameW
0x18000436e  test    eax, eax
0x180004370  jz      loc_180004559
0x180004376  xorps   xmm0, xmm0
0x180004379  movups  [rbp+240h+var_2A0], xmm0
0x18000437d  movups  [rbp+240h+var_290], xmm0
0x180004381  movups  [rbp+240h+var_280], xmm0
0x180004385  movups  [rbp+240h+var_270], xmm0
0x180004389  movups  [rbp+240h+var_260], xmm0
0x18000438d  movups  [rbp+240h+var_250], xmm0
0x180004391  movups  [rbp+240h+var_240], xmm0
0x180004395  movups  [rbp+240h+var_230], xmm0
0x180004399  call    cs:__imp_GetLastError
0x18000439f  cmp     eax, 7Ah ; 'z'
0x1800043a2  jz      short loc_1800043C4
0x1800043a4  mov     edx, 5Ch ; '\'; Ch
0x1800043a9  lea     rcx, [rbp+240h+Filename]; Str
0x1800043ad  call    cs:__imp_wcsrchr
0x1800043b3  test    rax, rax
0x1800043b6  jz      short loc_1800043BE
0x1800043b8  add     rax, 2
0x1800043bc  jmp     short loc_1800043CB
0x1800043be  lea     rax, [rbp+240h+Filename]
0x1800043c2  jmp     short loc_1800043CB
0x1800043c4  lea     rax, qword_18001A0D0
0x1800043cb  mov     ecx, 7FFFFFFEh
0x1800043d0  lea     r9, [rbp+240h+var_2A0]
0x1800043d4  mov     r8d, 40h ; '@'
0x1800043da  nop     word ptr [rax+rax+00h]
0x1800043e0  test    rcx, rcx
0x1800043e3  jz      short loc_180004402
0x1800043e5  movzx   edx, word ptr [rax]
0x1800043e8  test    dx, dx
0x1800043eb  jz      short loc_180004402
0x1800043ed  mov     [r9], dx
0x1800043f1  add     rax, 2
0x1800043f5  add     r9, 2
0x1800043f9  dec     rcx
0x1800043fc  sub     r8, 1
0x180004400  jnz     short loc_1800043E0
0x180004402  xor     eax, eax
0x180004404  lea     rdx, [r9-2]
0x180004408  test    r8, r8
0x18000440b  mov     ecx, 8007007Ah
0x180004410  cmovnz  rdx, r9
0x180004414  cmovnz  ecx, eax; int
0x180004417  mov     [rdx], ax
0x18000441a  jnz     short loc_180004426
0x18000441c  mov     edx, 212h; unsigned int
0x180004421  call    ?DoStackCaptureDirect@@YAXJI@Z; DoStackCaptureDirect(long,uint)
0x180004426  mov     eax, cs:dword_18001F268
0x18000442c  cmp     eax, 5
0x18000442f  jbe     loc_180004559
0x180004435  mov     rcx, cs:qword_18001F280
0x18000443c  mov     rdx, 400000000000h
0x180004446  mov     rax, cs:qword_18001F278
0x18000444d  test    rdx, rax
0x180004450  jz      loc_180004559
0x180004456  mov     rax, rcx
0x180004459  and     rax, rdx
0x18000445c  cmp     rax, rcx
0x18000445f  jnz     loc_180004559
0x180004465  lea     rax, [rsp+340h+var_310]
0x18000446a  mov     [rsp+340h+var_310], ebx
0x18000446e  mov     [rbp+240h+var_2B0], rax
0x180004472  lea     rcx, [rbp+240h+var_2A0]
0x180004476  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000447d  mov     [rsp+340h+var_308], 1000000h
0x180004486  mov     [rbp+240h+var_2A8], 4
0x18000448e  xchg    ax, ax
0x180004490  cmp     word ptr [rcx+rax*2+2], 0
0x180004496  lea     rax, [rax+1]
0x18000449a  jnz     short loc_180004490
0x18000449c  lea     eax, ds:2[rax*2]
0x1800044a3  mov     [rsp+340h+var_2F8], rdx
0x1800044a8  mov     [rbp+240h+var_2B8], eax
0x1800044ab  lea     rcx, [rbp+240h+var_2A0]
0x1800044af  mov     [rbp+240h+var_2C0], rcx
0x1800044b3  lea     rax, [rsp+340h+var_308]
0x1800044b8  mov     [rsp+340h+var_2D0], rax
0x1800044bd  lea     rcx, _TraceLoggingMetadata
0x1800044c4  movzx   eax, cs:word_18001ADF3
0x1800044cb  lea     rdx, [rsp+340h+var_300]
0x1800044d0  mov     [rsp+340h+var_2FC], eax
0x1800044d4  xor     r9d, r9d
0x1800044d7  mov     rax, cs:off_18001F270
0x1800044de  xor     r8d, r8d
0x1800044e1  mov     [rsp+340h+var_2F0], rax
0x1800044e6  mov     [rbp+240h+var_2B4], 0
0x1800044ed  mov     [rsp+340h+var_2C8], 8
0x1800044f6  mov     [rsp+340h+var_300], 0B000000h
0x1800044fe  movzx   eax, word ptr [rax]
0x180004501  mov     [rsp+340h+var_2E8], eax
0x180004505  lea     rax, byte_18001ADFD
0x18000450c  mov     [rsp+340h+var_2E0], rax
0x180004511  lea     rax, _TraceLoggingMetadataEnd
0x180004518  sub     eax, ecx
0x18000451a  mov     [rsp+340h+var_2E4], 2
0x180004522  mov     [rsp+340h+var_2D8], 3Ch ; '<'
0x18000452a  mov     [rsp+340h+var_2D4], 1
0x180004532  mov     [rsp+340h+var_30C], eax
0x180004536  mov     eax, [rsp+340h+var_30C]
0x18000453a  mov     rcx, cs:qword_18001F288
0x180004541  lea     rax, [rsp+340h+var_2F0]
0x180004546  mov     [rsp+340h+var_318], rax
0x18000454b  mov     [rsp+340h+var_320], 5
0x180004553  call    cs:__imp_EtwEventWriteTransfer
0x180004559  lea     rcx, ?s_cs@CDwmHwndData@@0VCDwmCS@@A; lpCriticalSection
0x180004560  mov     byte ptr [rdi+rbx], 1
0x180004564  call    cs:__imp_LeaveCriticalSection
0x18000456a  mov     rcx, [rbp+240h+var_10]
0x180004571  xor     rcx, rsp; StackCookie
0x180004574  call    __security_check_cookie
0x180004579  lea     r11, [rsp+340h+var_s0]
0x180004581  mov     rbx, [r11+18h]
0x180004585  mov     rdi, [r11+20h]
0x180004589  mov     rsp, r11
0x18000458c  pop     rbp
0x18000458d  retn
```
