# NcaScriptLogsGenerateLogsAndCaptureFile

- ea: `0x18000ae34`
- end: `0x18000b05c`
- name: `NcaScriptLogsGenerateLogsAndCaptureFile`
- size: `552`
- prototype: `__int64 __fastcall(unsigned __int16 *, HANDLE *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180007954`

## callees

- `0x180003770`
- `0x180004f34`
- `0x18000673c`
- `0x18000966c`
- `0x180009b6c`
- `0x180009c4c`
- `0x18000a398`
- `0x18000a954`
- `0x18000ae34`
- `0x180018fd4`
- `0x180019100`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000ae6b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000ae6b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aed4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aed4`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000aec2`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000aec2`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000b024`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000b024`

## pseudocode

```c
__int64 __fastcall NcaScriptLogsGenerateLogsAndCaptureFile(unsigned __int16 *a1, HANDLE *a2)
{
  void *v3; // rdi
  int v4; // r15d
  void *v6; // r14
  __int64 v7; // rax
  BOOL v8; // esi
  unsigned int LastError; // eax
  unsigned int v10; // ebx
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r9
  unsigned int v14; // eax
  int v16; // [rsp+68h] [rbp+10h] BYREF
  void *v17; // [rsp+70h] [rbp+18h] BYREF
  LPVOID lpMem; // [rsp+78h] [rbp+20h] BYREF

  v16 = 1;
  v17 = 0;
  lpMem = 0;
  v3 = 0;
  v4 = 0;
  AcquireSRWLockShared(&SRWLock);
  NcaConfigMgrGetString(2, &lpMem);
  NcaExcludeShareLockLeave(1, &SRWLock);
  v6 = lpMem;
  if ( !lpMem )
    goto LABEL_23;
  v7 = -1;
  do
    ++v7;
  while ( *((_WORD *)lpMem + v7) );
  if ( v7 )
  {
    v8 = SetThreadToken(0, a2[4]);
    if ( v8 )
    {
      NcaScriptLogsLoadStrings();
      v4 = 1;
      v14 = NcaScriptLogsOpenLogFile(a1, &v17);
      v10 = v14;
      if ( v14 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 80, WPP_f1adb992d8ea37c37fe83ded2c90ce95_Traceguids, v14);
        v3 = v17;
      }
      else
      {
        v3 = v17;
        LastError = NcaScriptLogsWriteHeader(v17, (struct NCA_USER_ *)a2);
        v10 = LastError;
        if ( LastError )
        {
          v11 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v12 = 81;
            goto LABEL_9;
          }
        }
        else
        {
          LastError = NcaScriptLogsWriteBody(v3, a2, &v16);
          v10 = LastError;
          if ( LastError )
          {
            v11 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v12 = 82;
              goto LABEL_9;
            }
          }
        }
      }
    }
    else
    {
      LastError = GetLastError();
      v10 = LastError;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v12 = 79;
LABEL_9:
        v13 = LastError;
LABEL_26:
        WPP_SF_d(v11[2], v12, WPP_f1adb992d8ea37c37fe83ded2c90ce95_Traceguids, v13);
      }
    }
  }
  else
  {
LABEL_23:
    v8 = 0;
    v10 = 5;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v12 = 78;
      v13 = 5;
      goto LABEL_26;
    }
  }
  if ( a2[4] && v8 && v16 )
    RevertToSelf();
  NcaFree(v6);
  NcaCloseHandle(v3);
  if ( v4 )
    NcaScriptLogsFreeStrings();
  return v10;
}

```

## disassembly

```asm
0x18000ae34  push    rbx
0x18000ae36  push    rbp
0x18000ae37  push    rsi
0x18000ae38  push    rdi
0x18000ae39  push    r12
0x18000ae3b  push    r14
0x18000ae3d  push    r15
0x18000ae3f  sub     rsp, 20h
0x18000ae43  xor     r12d, r12d
0x18000ae46  mov     [rsp+58h+arg_8], 1
0x18000ae4e  mov     rbx, rcx
0x18000ae51  mov     [rsp+58h+arg_10], r12
0x18000ae56  lea     rcx, SRWLock; SRWLock
0x18000ae5d  mov     [rsp+58h+lpMem], r12
0x18000ae62  mov     edi, r12d
0x18000ae65  mov     r15d, r12d
0x18000ae68  mov     rbp, rdx
0x18000ae6b  call    cs:__imp_AcquireSRWLockShared
0x18000ae72  nop     dword ptr [rax+rax+00h]
0x18000ae77  lea     rdx, [rsp+58h+lpMem]
0x18000ae7c  lea     ecx, [r12+2]
0x18000ae81  call    NcaConfigMgrGetString
0x18000ae86  lea     rdx, SRWLock
0x18000ae8d  lea     ecx, [r12+1]
0x18000ae92  call    NcaExcludeShareLockLeave
0x18000ae97  mov     r14, [rsp+58h+lpMem]
0x18000ae9c  test    r14, r14
0x18000ae9f  jz      loc_18000AFDC
0x18000aea5  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000aea9  inc     rax
0x18000aeac  cmp     [r14+rax*2], r12w
0x18000aeb1  jnz     short loc_18000AEA9
0x18000aeb3  test    rax, rax
0x18000aeb6  jz      loc_18000AFDC
0x18000aebc  mov     rdx, [rbp+20h]; Token
0x18000aec0  xor     ecx, ecx; Thread
0x18000aec2  call    cs:__imp_SetThreadToken
0x18000aec9  nop     dword ptr [rax+rax+00h]
0x18000aece  mov     esi, eax
0x18000aed0  test    eax, eax
0x18000aed2  jnz     short loc_18000AF0E
0x18000aed4  call    cs:__imp_GetLastError
0x18000aedb  nop     dword ptr [rax+rax+00h]
0x18000aee0  mov     ebx, eax
0x18000aee2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000aee9  lea     rdx, WPP_GLOBAL_Control
0x18000aef0  cmp     rcx, rdx
0x18000aef3  jz      loc_18000B013
0x18000aef9  test    byte ptr [rcx+1Ch], 1
0x18000aefd  jz      loc_18000B013
0x18000af03  lea     edx, [rsi+4Fh]
0x18000af06  mov     r9d, eax
0x18000af09  jmp     loc_18000B003
0x18000af0e  call    ?NcaScriptLogsLoadStrings@@YAXXZ; NcaScriptLogsLoadStrings(void)
0x18000af13  lea     rdx, [rsp+58h+arg_10]; void **
0x18000af18  mov     rcx, rbx; unsigned __int16 *
0x18000af1b  mov     r15d, 1
0x18000af21  call    ?NcaScriptLogsOpenLogFile@@YAKPEBGPEAPEAX@Z; NcaScriptLogsOpenLogFile(ushort const *,void * *)
0x18000af26  mov     ebx, eax
0x18000af28  test    eax, eax
0x18000af2a  jz      short loc_18000AF66
0x18000af2c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000af33  lea     rdx, WPP_GLOBAL_Control
0x18000af3a  cmp     rcx, rdx
0x18000af3d  jz      short loc_18000AF5C
0x18000af3f  test    [rcx+1Ch], r15b
0x18000af43  jz      short loc_18000AF5C
0x18000af45  mov     rcx, [rcx+10h]
0x18000af49  lea     edx, [r15+4Fh]
0x18000af4d  mov     r9d, eax
0x18000af50  lea     r8, WPP_f1adb992d8ea37c37fe83ded2c90ce95_Traceguids
0x18000af57  call    WPP_SF_d
0x18000af5c  mov     rdi, [rsp+58h+arg_10]
0x18000af61  jmp     loc_18000B013
0x18000af66  mov     rdi, [rsp+58h+arg_10]
0x18000af6b  mov     rdx, rbp; struct NCA_USER_ *
0x18000af6e  mov     rcx, rdi; void *
0x18000af71  call    ?NcaScriptLogsWriteHeader@@YAKPEAXPEAUNCA_USER_@@@Z; NcaScriptLogsWriteHeader(void *,NCA_USER_ *)
0x18000af76  mov     ebx, eax
0x18000af78  test    eax, eax
0x18000af7a  jz      short loc_18000AFA3
0x18000af7c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000af83  lea     rdx, WPP_GLOBAL_Control
0x18000af8a  cmp     rcx, rdx
0x18000af8d  jz      loc_18000B013
0x18000af93  test    [rcx+1Ch], r15b
0x18000af97  jz      short loc_18000B013
0x18000af99  mov     edx, 51h ; 'Q'
0x18000af9e  jmp     loc_18000AF06
0x18000afa3  lea     r8, [rsp+58h+arg_8]; int *
0x18000afa8  mov     rdx, rbp; struct NCA_USER_ *
0x18000afab  mov     rcx, rdi; void *
0x18000afae  call    ?NcaScriptLogsWriteBody@@YAKPEAXPEAUNCA_USER_@@PEAH@Z; NcaScriptLogsWriteBody(void *,NCA_USER_ *,int *)
0x18000afb3  mov     ebx, eax
0x18000afb5  test    eax, eax
0x18000afb7  jz      short loc_18000B013
0x18000afb9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000afc0  lea     rdx, WPP_GLOBAL_Control
0x18000afc7  cmp     rcx, rdx
0x18000afca  jz      short loc_18000B013
0x18000afcc  test    [rcx+1Ch], r15b
0x18000afd0  jz      short loc_18000B013
0x18000afd2  mov     edx, 52h ; 'R'
0x18000afd7  jmp     loc_18000AF06
0x18000afdc  mov     esi, r12d
0x18000afdf  mov     ebx, 5
0x18000afe4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000afeb  lea     rdx, WPP_GLOBAL_Control
0x18000aff2  cmp     rcx, rdx
0x18000aff5  jz      short loc_18000B013
0x18000aff7  test    byte ptr [rcx+1Ch], 1
0x18000affb  jz      short loc_18000B013
0x18000affd  lea     edx, [rbx+49h]
0x18000b000  mov     r9d, ebx
0x18000b003  mov     rcx, [rcx+10h]
0x18000b007  lea     r8, WPP_f1adb992d8ea37c37fe83ded2c90ce95_Traceguids
0x18000b00e  call    WPP_SF_d
0x18000b013  cmp     [rbp+20h], r12
0x18000b017  jz      short loc_18000B030
0x18000b019  test    esi, esi
0x18000b01b  jz      short loc_18000B030
0x18000b01d  cmp     [rsp+58h+arg_8], r12d
0x18000b022  jz      short loc_18000B030
0x18000b024  call    cs:__imp_RevertToSelf
0x18000b02b  nop     dword ptr [rax+rax+00h]
0x18000b030  mov     rcx, r14; lpMem
0x18000b033  call    NcaFree
0x18000b038  mov     rcx, rdi
0x18000b03b  call    NcaCloseHandle
0x18000b040  test    r15d, r15d
0x18000b043  jz      short loc_18000B04A
0x18000b045  call    ?NcaScriptLogsFreeStrings@@YAXXZ; NcaScriptLogsFreeStrings(void)
0x18000b04a  mov     eax, ebx
0x18000b04c  add     rsp, 20h
0x18000b050  pop     r15
0x18000b052  pop     r14
0x18000b054  pop     r12
0x18000b056  pop     rdi
0x18000b057  pop     rsi
0x18000b058  pop     rbp
0x18000b059  pop     rbx
0x18000b05a  retn
```
