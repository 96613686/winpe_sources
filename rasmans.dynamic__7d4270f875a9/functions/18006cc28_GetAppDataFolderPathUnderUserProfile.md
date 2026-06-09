# GetAppDataFolderPathUnderUserProfile

- ea: `0x18006cc28`
- end: `0x18006d105`
- name: `GetAppDataFolderPathUnderUserProfile`
- size: `1245`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x18006b0b4`

## callees

- `0x180005bcc`
- `0x180005bfc`
- `0x18005f32c`
- `0x18005fbf4`
- `0x18006cc28`
- `0x1800e8e96`
- `0x1800e8ef0`

## import_xrefs

- `msvcrt!wcschr` at `0x18006d042`
- `msvcrt!wcschr` at `0x18006d042`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006cce3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006cce3`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18006cd02`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18006cd02`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18006cd2f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18006cd2f`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18006cd45`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18006cd45`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006d09b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006d09b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006cd16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006cd59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006cee3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006cd16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006cd59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006cee3`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18006d07d`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18006d07d`
- `USERENV!GetProfilesDirectoryW` at `0x18006ced3`
- `USERENV!GetProfilesDirectoryW` at `0x18006ced3`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x18006ce82`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x18006ce82`

## pseudocode

```c
__int64 __fastcall GetAppDataFolderPathUnderUserProfile(__int64 *a1)
{
  struct _LIST_ENTRY *v2; // rbx
  DWORD v3; // edi
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  DWORD v6; // ebx
  HANDLE CurrentProcess; // rax
  DWORD v8; // eax
  struct _LIST_ENTRY *v9; // rcx
  __int64 v10; // rdx
  DWORD SidFromToken; // eax
  __int64 v13; // rdx
  __int64 v14; // r9
  unsigned __int16 BasicProfileFolderPath; // ax
  __int64 v16; // r9
  WCHAR *v17; // rax
  unsigned __int64 v18; // r10
  unsigned int v19; // esi
  __int64 v20; // r8
  _WORD *v21; // rax
  wchar_t *v22; // rax
  const wchar_t *v23; // rcx
  __int64 v24; // rax
  DWORD cchSize; // [rsp+20h] [rbp-E0h] BYREF
  void *TokenHandle; // [rsp+28h] [rbp-D8h] BYREF
  HGLOBAL hMem; // [rsp+30h] [rbp-D0h]
  _BYTE v28[528]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR ProfileDir[264]; // [rsp+250h] [rbp+150h] BYREF

  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 767, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids);
    v2 = WPP_GLOBAL_Control;
  }
  memset_0(v28, 0, 0x20Au);
  memset_0(ProfileDir, 0, 0x20Au);
  cchSize = 0;
  TokenHandle = 0;
  hMem = 0;
  if ( a1 )
  {
    *a1 = 0;
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 0xCu, 1, &TokenHandle) )
      goto LABEL_32;
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError == 1008 )
    {
      CurrentProcess = GetCurrentProcess();
      if ( !OpenProcessToken(CurrentProcess, 0xCu, &TokenHandle) )
      {
        v8 = GetLastError();
        v6 = v8;
        if ( v8 )
        {
          v9 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
            return v6;
          if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0 || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
            goto LABEL_16;
          WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 768, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v8);
        }
        v9 = WPP_GLOBAL_Control;
LABEL_16:
        if ( v9 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control || SBYTE4(v9[1].Blink) >= 0 || BYTE1(v9[1].Blink) < 6u )
          return v6;
        v10 = 769;
        goto LABEL_20;
      }
LABEL_32:
      SidFromToken = GetSidFromToken(TokenHandle);
      v3 = SidFromToken;
      if ( SidFromToken )
      {
        v2 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          || SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0
          || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
        {
          goto LABEL_74;
        }
        v13 = 772;
        v14 = SidFromToken;
      }
      else
      {
        BasicProfileFolderPath = GetBasicProfileFolderPath(7, hMem, v28, 261);
        v3 = BasicProfileFolderPath;
        if ( BasicProfileFolderPath )
        {
          v2 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            || SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0
            || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
          {
            goto LABEL_74;
          }
          v13 = 773;
          v14 = BasicProfileFolderPath;
        }
        else
        {
          cchSize = 261;
          if ( !GetProfilesDirectoryW(ProfileDir, &cchSize) )
          {
            v3 = GetLastError();
            goto LABEL_73;
          }
          v16 = 261;
          v17 = ProfileDir;
          do
          {
            if ( !*v17 )
              break;
            ++v17;
            --v16;
          }
          while ( v16 );
          v18 = (261 - v16) & -(__int64)(v16 != 0);
          v19 = v16 == 0 ? 0x57 : 0;
          if ( !v16 )
          {
            v2 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
            {
              WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 774, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v19);
              v2 = WPP_GLOBAL_Control;
            }
            v3 = v19;
            goto LABEL_74;
          }
          v20 = 261;
          v21 = v28;
          do
          {
            if ( !*v21 )
              break;
            ++v21;
            --v20;
          }
          while ( v20 );
          v3 = v20 == 0 ? 0x57 : 0;
          if ( v20 )
          {
            if ( ((261 - v20) & (unsigned __int64)-(__int64)(v20 != 0)) >= v18 + 1 )
            {
              if ( v18 < 0x104 )
              {
                v22 = wcschr((const wchar_t *)&v28[2 * v18 + 2], 0x5Cu);
                v23 = v22 + 1;
                if ( !v22 )
                  v23 = 0;
                v24 = StrDup(v23);
                *a1 = v24;
                if ( !v24 )
                  v3 = 8;
              }
              goto LABEL_73;
            }
            v3 = 10;
            v2 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              || SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0
              || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
            {
              goto LABEL_74;
            }
            v13 = 776;
          }
          else
          {
            v2 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              || SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0
              || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
            {
              goto LABEL_74;
            }
            v13 = 775;
          }
          v14 = v3;
        }
      }
      WPP_SF_d(v2[1].Flink, v13, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v14);
LABEL_73:
      v2 = WPP_GLOBAL_Control;
      goto LABEL_74;
    }
    if ( LastError )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        return v6;
      if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0 || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
        goto LABEL_28;
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 770, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, LastError);
    }
    v9 = WPP_GLOBAL_Control;
LABEL_28:
    if ( v9 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control || SBYTE4(v9[1].Blink) >= 0 || BYTE1(v9[1].Blink) < 6u )
      return v6;
    v10 = 771;
LABEL_20:
    WPP_SF_d(v9[1].Flink, v10, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v6);
    return v6;
  }
  v3 = 87;
LABEL_74:
  if ( hMem )
  {
    GlobalFree(hMem);
    v2 = WPP_GLOBAL_Control;
  }
  if ( TokenHandle != (void *)-1LL )
  {
    CloseHandle(TokenHandle);
    v2 = WPP_GLOBAL_Control;
  }
  if ( v2 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && SBYTE4(v2[1].Blink) < 0 && BYTE1(v2[1].Blink) >= 6u )
    WPP_SF_d(v2[1].Flink, 777, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v3);
  return v3;
}

```

## disassembly

```asm
0x18006cc28  mov     [rsp-8+arg_8], rbx
0x18006cc2d  mov     [rsp-8+arg_10], rsi
0x18006cc32  push    rbp
0x18006cc33  push    rdi
0x18006cc34  push    r13
0x18006cc36  push    r14
0x18006cc38  push    r15
0x18006cc3a  lea     rbp, [rsp-370h]
0x18006cc42  sub     rsp, 470h
0x18006cc49  mov     rax, cs:__security_cookie
0x18006cc50  xor     rax, rsp
0x18006cc53  mov     [rbp+390h+var_30], rax
0x18006cc5a  mov     r14, rcx
0x18006cc5d  mov     rbx, cs:WPP_GLOBAL_Control
0x18006cc64  lea     r13, WPP_GLOBAL_Control
0x18006cc6b  lea     rsi, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x18006cc72  cmp     rbx, r13
0x18006cc75  jz      short loc_18006CC9B
0x18006cc77  test    byte ptr [rbx+1Ch], 80h
0x18006cc7b  jz      short loc_18006CC9B
0x18006cc7d  cmp     byte ptr [rbx+19h], 6
0x18006cc81  jb      short loc_18006CC9B
0x18006cc83  mov     rcx, [rbx+10h]
0x18006cc87  mov     edx, 2FFh
0x18006cc8c  mov     r8, rsi
0x18006cc8f  call    WPP_SF_
0x18006cc94  mov     rbx, cs:WPP_GLOBAL_Control
0x18006cc9b  mov     edi, 20Ah
0x18006cca0  lea     rcx, [rsp+490h+var_450]; void *
0x18006cca5  mov     r8d, edi; Size
0x18006cca8  xor     edx, edx; Val
0x18006ccaa  call    memset_0
0x18006ccaf  mov     r8d, edi; Size
0x18006ccb2  lea     rcx, [rbp+390h+ProfileDir]; void *
0x18006ccb9  xor     edx, edx; Val
0x18006ccbb  call    memset_0
0x18006ccc0  xor     r15d, r15d
0x18006ccc3  mov     [rsp+490h+cchSize], r15d
0x18006ccc8  mov     [rsp+490h+TokenHandle], r15
0x18006cccd  mov     [rsp+490h+hMem], r15
0x18006ccd2  test    r14, r14
0x18006ccd5  jnz     short loc_18006CCE0
0x18006ccd7  lea     edi, [r15+57h]
0x18006ccdb  jmp     loc_18006D073
0x18006cce0  mov     [r14], r15
0x18006cce3  call    cs:__imp_GetCurrentThread
0x18006ccea  nop     dword ptr [rax+rax+00h]
0x18006ccef  mov     edi, 0Ch
0x18006ccf4  lea     r9, [rsp+490h+TokenHandle]; TokenHandle
0x18006ccf9  mov     rcx, rax; ThreadHandle
0x18006ccfc  mov     edx, edi; DesiredAccess
0x18006ccfe  lea     r8d, [rdi-0Bh]; OpenAsSelf
0x18006cd02  call    cs:__imp_OpenThreadToken
0x18006cd09  nop     dword ptr [rax+rax+00h]
0x18006cd0e  test    eax, eax
0x18006cd10  jnz     loc_18006CE19
0x18006cd16  call    cs:__imp_GetLastError
0x18006cd1d  nop     dword ptr [rax+rax+00h]
0x18006cd22  mov     ebx, eax
0x18006cd24  cmp     eax, 3F0h
0x18006cd29  jnz     loc_18006CDCA
0x18006cd2f  call    cs:__imp_GetCurrentProcess
0x18006cd36  nop     dword ptr [rax+rax+00h]
0x18006cd3b  lea     r8, [rsp+490h+TokenHandle]; TokenHandle
0x18006cd40  mov     edx, edi; DesiredAccess
0x18006cd42  mov     rcx, rax; ProcessHandle
0x18006cd45  call    cs:__imp_OpenProcessToken
0x18006cd4c  nop     dword ptr [rax+rax+00h]
0x18006cd51  test    eax, eax
0x18006cd53  jnz     loc_18006CE19
0x18006cd59  call    cs:__imp_GetLastError
0x18006cd60  nop     dword ptr [rax+rax+00h]
0x18006cd65  mov     ebx, eax
0x18006cd67  test    eax, eax
0x18006cd69  jz      short loc_18006CD97
0x18006cd6b  mov     rcx, cs:WPP_GLOBAL_Control
0x18006cd72  cmp     rcx, r13
0x18006cd75  jz      short loc_18006CDC3
0x18006cd77  test    byte ptr [rcx+1Ch], 80h
0x18006cd7b  jz      short loc_18006CD9E
0x18006cd7d  cmp     byte ptr [rcx+19h], 2
0x18006cd81  jb      short loc_18006CD9E
0x18006cd83  mov     rcx, [rcx+10h]
0x18006cd87  mov     edx, 300h
0x18006cd8c  mov     r9d, eax
0x18006cd8f  mov     r8, rsi
0x18006cd92  call    WPP_SF_d
0x18006cd97  mov     rcx, cs:WPP_GLOBAL_Control
0x18006cd9e  cmp     rcx, r13
0x18006cda1  jz      short loc_18006CDC3
0x18006cda3  test    byte ptr [rcx+1Ch], 80h
0x18006cda7  jz      short loc_18006CDC3
0x18006cda9  cmp     byte ptr [rcx+19h], 6
0x18006cdad  jb      short loc_18006CDC3
0x18006cdaf  mov     edx, 301h
0x18006cdb4  mov     rcx, [rcx+10h]
0x18006cdb8  mov     r9d, ebx
0x18006cdbb  mov     r8, rsi
0x18006cdbe  call    WPP_SF_d
0x18006cdc3  mov     eax, ebx
0x18006cdc5  jmp     loc_18006D0D9
0x18006cdca  test    ebx, ebx
0x18006cdcc  jz      short loc_18006CDFA
0x18006cdce  mov     rcx, cs:WPP_GLOBAL_Control
0x18006cdd5  cmp     rcx, r13
0x18006cdd8  jz      short loc_18006CDC3
0x18006cdda  test    byte ptr [rcx+1Ch], 80h
0x18006cdde  jz      short loc_18006CE01
0x18006cde0  cmp     byte ptr [rcx+19h], 2
0x18006cde4  jb      short loc_18006CE01
0x18006cde6  mov     rcx, [rcx+10h]
0x18006cdea  mov     edx, 302h
0x18006cdef  mov     r9d, ebx
0x18006cdf2  mov     r8, rsi
0x18006cdf5  call    WPP_SF_d
0x18006cdfa  mov     rcx, cs:WPP_GLOBAL_Control
0x18006ce01  cmp     rcx, r13
0x18006ce04  jz      short loc_18006CDC3
0x18006ce06  test    byte ptr [rcx+1Ch], 80h
0x18006ce0a  jz      short loc_18006CDC3
0x18006ce0c  cmp     byte ptr [rcx+19h], 6
0x18006ce10  jb      short loc_18006CDC3
0x18006ce12  mov     edx, 303h
0x18006ce17  jmp     short loc_18006CDB4
0x18006ce19  mov     rcx, [rsp+490h+TokenHandle]; TokenHandle
0x18006ce1e  lea     rdx, [rsp+490h+hMem]
0x18006ce23  call    GetSidFromToken
0x18006ce28  mov     edi, eax
0x18006ce2a  test    eax, eax
0x18006ce2c  jz      short loc_18006CE6B
0x18006ce2e  mov     rbx, cs:WPP_GLOBAL_Control
0x18006ce35  cmp     rbx, r13
0x18006ce38  jz      loc_18006D073
0x18006ce3e  test    byte ptr [rbx+1Ch], 80h
0x18006ce42  jz      loc_18006D073
0x18006ce48  cmp     byte ptr [rbx+19h], 2
0x18006ce4c  jb      loc_18006D073
0x18006ce52  mov     edx, 304h
0x18006ce57  mov     r9d, eax
0x18006ce5a  mov     r8, rsi
0x18006ce5d  mov     rcx, [rbx+10h]
0x18006ce61  call    WPP_SF_d
0x18006ce66  jmp     loc_18006D06C
0x18006ce6b  mov     rdx, [rsp+490h+hMem]
0x18006ce70  lea     r8, [rsp+490h+var_450]
0x18006ce75  mov     ebx, 105h
0x18006ce7a  mov     ecx, 7
0x18006ce7f  mov     r9d, ebx
0x18006ce82  call    cs:__imp_GetBasicProfileFolderPath
0x18006ce89  nop     dword ptr [rax+rax+00h]
0x18006ce8e  movzx   edi, ax
0x18006ce91  test    edi, edi
0x18006ce93  jz      short loc_18006CEC3
0x18006ce95  mov     rbx, cs:WPP_GLOBAL_Control
0x18006ce9c  cmp     rbx, r13
0x18006ce9f  jz      loc_18006D073
0x18006cea5  test    byte ptr [rbx+1Ch], 80h
0x18006cea9  jz      loc_18006D073
0x18006ceaf  cmp     byte ptr [rbx+19h], 2
0x18006ceb3  jb      loc_18006D073
0x18006ceb9  mov     edx, 305h
0x18006cebe  mov     r9d, edi
0x18006cec1  jmp     short loc_18006CE5A
0x18006cec3  lea     rdx, [rsp+490h+cchSize]; lpcchSize
0x18006cec8  mov     [rsp+490h+cchSize], ebx
0x18006cecc  lea     rcx, [rbp+390h+ProfileDir]; lpProfileDir
0x18006ced3  call    cs:__imp_GetProfilesDirectoryW
0x18006ceda  nop     dword ptr [rax+rax+00h]
0x18006cedf  test    eax, eax
0x18006cee1  jnz     short loc_18006CEF6
0x18006cee3  call    cs:__imp_GetLastError
0x18006ceea  nop     dword ptr [rax+rax+00h]
0x18006ceef  mov     edi, eax
0x18006cef1  jmp     loc_18006D06C
0x18006cef6  mov     r9, rbx
0x18006cef9  lea     rax, [rbp+390h+ProfileDir]
0x18006cf00  cmp     [rax], r15w
0x18006cf04  jz      short loc_18006CF10
0x18006cf06  add     rax, 2
0x18006cf0a  sub     r9, 1
0x18006cf0e  jnz     short loc_18006CF00
0x18006cf10  mov     rcx, rbx
0x18006cf13  mov     rax, r9
0x18006cf16  sub     rcx, r9
0x18006cf19  mov     r8, r9
0x18006cf1c  neg     rax
0x18006cf1f  mov     edi, 57h ; 'W'
0x18006cf24  mov     rax, r9
0x18006cf27  sbb     rdx, rdx
0x18006cf2a  and     rdx, rcx
0x18006cf2d  neg     r8
0x18006cf30  sbb     r10, r10
0x18006cf33  and     r10, rdx
0x18006cf36  neg     rax
0x18006cf39  sbb     esi, esi
0x18006cf3b  not     esi
0x18006cf3d  and     esi, edi
0x18006cf3f  test    r9, r9
0x18006cf42  jnz     short loc_18006CF82
0x18006cf44  mov     rbx, cs:WPP_GLOBAL_Control
0x18006cf4b  cmp     rbx, r13
0x18006cf4e  jz      short loc_18006CF7B
0x18006cf50  test    byte ptr [rbx+1Ch], 80h
0x18006cf54  jz      short loc_18006CF7B
0x18006cf56  cmp     byte ptr [rbx+19h], 2
0x18006cf5a  jb      short loc_18006CF7B
0x18006cf5c  mov     rcx, [rbx+10h]
0x18006cf60  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x18006cf67  mov     edx, 306h
0x18006cf6c  mov     r9d, esi
0x18006cf6f  call    WPP_SF_d
0x18006cf74  mov     rbx, cs:WPP_GLOBAL_Control
0x18006cf7b  mov     edi, esi
0x18006cf7d  jmp     loc_18006D073
0x18006cf82  mov     r8, rbx
0x18006cf85  lea     rax, [rsp+490h+var_450]
0x18006cf8a  cmp     [rax], r15w
0x18006cf8e  jz      short loc_18006CF9A
0x18006cf90  add     rax, 2
0x18006cf94  sub     r8, 1
0x18006cf98  jnz     short loc_18006CF8A
0x18006cf9a  sub     rbx, r8
0x18006cf9d  mov     rax, r8
0x18006cfa0  neg     rax
0x18006cfa3  mov     rdx, r8
0x18006cfa6  mov     rax, r8
0x18006cfa9  sbb     rcx, rcx
0x18006cfac  and     rcx, rbx
0x18006cfaf  neg     rdx
0x18006cfb2  sbb     r9, r9
0x18006cfb5  and     r9, rcx
0x18006cfb8  neg     rax
0x18006cfbb  sbb     ecx, ecx
0x18006cfbd  not     ecx
0x18006cfbf  and     edi, ecx
0x18006cfc1  test    r8, r8
0x18006cfc4  jnz     short loc_18006CFFE
0x18006cfc6  mov     rbx, cs:WPP_GLOBAL_Control
0x18006cfcd  cmp     rbx, r13
0x18006cfd0  jz      loc_18006D073
0x18006cfd6  test    byte ptr [rbx+1Ch], 80h
0x18006cfda  jz      loc_18006D073
0x18006cfe0  cmp     byte ptr [rbx+19h], 2
0x18006cfe4  jb      loc_18006D073
0x18006cfea  mov     edx, 307h
0x18006cfef  mov     r9d, edi
0x18006cff2  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x18006cff9  jmp     loc_18006CE5D
0x18006cffe  lea     rax, [r10+1]
0x18006d002  cmp     r9, rax
0x18006d005  jnb     short loc_18006D02B
0x18006d007  mov     edi, 0Ah
0x18006d00c  mov     rbx, cs:WPP_GLOBAL_Control
0x18006d013  cmp     rbx, r13
0x18006d016  jz      short loc_18006D073
0x18006d018  test    byte ptr [rbx+1Ch], 80h
0x18006d01c  jz      short loc_18006D073
0x18006d01e  cmp     byte ptr [rbx+19h], 2
0x18006d022  jb      short loc_18006D073
0x18006d024  mov     edx, 308h
0x18006d029  jmp     short loc_18006CFEF
0x18006d02b  cmp     r10, 104h
0x18006d032  jnb     short loc_18006D06C
0x18006d034  lea     rcx, [rsp+490h+var_44E]
0x18006d039  mov     edx, 5Ch ; '\'; Ch
0x18006d03e  lea     rcx, [rcx+r10*2]; Str
0x18006d042  call    cs:__imp_wcschr
0x18006d049  nop     dword ptr [rax+rax+00h]
0x18006d04e  test    rax, rax
0x18006d051  lea     rcx, [rax+2]
0x18006d055  cmovz   rcx, rax; pszSrc
0x18006d059  call    StrDup
0x18006d05e  test    rax, rax
0x18006d061  mov     [r14], rax
0x18006d064  mov     ecx, 8
0x18006d069  cmovz   edi, ecx
0x18006d06c  mov     rbx, cs:WPP_GLOBAL_Control
0x18006d073  mov     rcx, [rsp+490h+hMem]; hMem
0x18006d078  test    rcx, rcx
0x18006d07b  jz      short loc_18006D090
0x18006d07d  call    cs:__imp_GlobalFree
0x18006d084  nop     dword ptr [rax+rax+00h]
0x18006d089  mov     rbx, cs:WPP_GLOBAL_Control
0x18006d090  mov     rcx, [rsp+490h+TokenHandle]; hObject
0x18006d095  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18006d099  jz      short loc_18006D0AE
0x18006d09b  call    cs:__imp_CloseHandle
0x18006d0a2  nop     dword ptr [rax+rax+00h]
0x18006d0a7  mov     rbx, cs:WPP_GLOBAL_Control
0x18006d0ae  cmp     rbx, r13
0x18006d0b1  jz      short loc_18006D0D7
0x18006d0b3  test    byte ptr [rbx+1Ch], 80h
0x18006d0b7  jz      short loc_18006D0D7
0x18006d0b9  cmp     byte ptr [rbx+19h], 6
0x18006d0bd  jb      short loc_18006D0D7
0x18006d0bf  mov     rcx, [rbx+10h]
0x18006d0c3  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x18006d0ca  mov     edx, 309h
0x18006d0cf  mov     r9d, edi
0x18006d0d2  call    WPP_SF_d
  ... truncated ...
```
