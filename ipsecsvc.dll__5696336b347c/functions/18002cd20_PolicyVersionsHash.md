# PolicyVersionsHash

- ea: `0x18002cd20`
- end: `0x18002ce71`
- name: `PolicyVersionsHash`
- size: `337`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000adac`

## callees

- `0x18000e510`
- `0x18002cd20`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18002cd50`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18002cd50`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002cd3d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002cd3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cd81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cdeb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cd81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cdeb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ce59`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ce59`
- `api-ms-win-security-grouppolicy-l1-1-0!FreeGPOListInternalW` at `0x18002ce4e`
- `api-ms-win-security-grouppolicy-l1-1-0!FreeGPOListInternalW` at `0x18002ce4e`
- `api-ms-win-security-grouppolicy-l1-1-0!GetGPOListInternalW` at `0x18002cdc2`
- `api-ms-win-security-grouppolicy-l1-1-0!GetGPOListInternalW` at `0x18002cdc2`

## pseudocode

```c
__int64 __fastcall PolicyVersionsHash(_DWORD *a1)
{
  HANDLE CurrentProcess; // rax
  unsigned int GPOListInternalW; // edi
  __int64 v4; // rbx
  DWORD LastError; // eax
  __int64 v6; // rdx
  __int64 v7; // rcx
  int v8; // r9d
  int v9; // r8d
  _WORD *v10; // rdx
  int v11; // r10d
  int v12; // eax
  __int64 v14; // [rsp+48h] [rbp+10h] BYREF
  void *TokenHandle; // [rsp+50h] [rbp+18h] BYREF

  v14 = 0;
  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  GPOListInternalW = OpenProcessToken(CurrentProcess, 0xF01FFu, &TokenHandle);
  if ( GPOListInternalW )
  {
    GPOListInternalW = GetGPOListInternalW(TokenHandle, 0, 0, 0, 1, &v14);
    if ( GPOListInternalW )
    {
      v7 = v14;
      v8 = 1;
      v9 = 0;
      while ( v7 )
      {
        v10 = (_WORD *)(v7 + 32);
        v11 = 0;
        if ( v7 != -32 )
        {
          do
          {
            if ( !*v10 )
              break;
            v11 += (unsigned __int16)*v10++;
          }
          while ( v10 );
        }
        v12 = *(_DWORD *)(v7 + 4);
        v7 = *(_QWORD *)(v7 + 144);
        v9 += v8 * (v11 + v12);
        ++v8;
      }
      *a1 = v9;
    }
    else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v4 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      LastError = GetLastError();
      v6 = 137;
      goto LABEL_5;
    }
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    v4 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    LastError = GetLastError();
    v6 = 136;
LABEL_5:
    WPP_SF_d(v4, v6, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids, LastError);
  }
  if ( v14 )
    FreeGPOListInternalW();
  CloseHandle(TokenHandle);
  return GPOListInternalW;
}

```

## disassembly

```asm
0x18002cd20  mov     rax, rsp
0x18002cd23  mov     [rax+8], rbx
0x18002cd27  mov     [rax+20h], rsi
0x18002cd2b  push    rdi
0x18002cd2c  sub     rsp, 30h
0x18002cd30  xor     esi, esi
0x18002cd32  mov     rbx, rcx
0x18002cd35  mov     [rax+10h], rsi
0x18002cd39  mov     [rax+18h], rsi
0x18002cd3d  call    cs:__imp_GetCurrentProcess
0x18002cd43  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x18002cd48  mov     edx, 0F01FFh; DesiredAccess
0x18002cd4d  mov     rcx, rax; ProcessHandle
0x18002cd50  call    cs:__imp_OpenProcessToken
0x18002cd56  mov     edi, eax
0x18002cd58  test    eax, eax
0x18002cd5a  jnz     short loc_18002CDA3
0x18002cd5c  mov     rbx, cs:WPP_GLOBAL_Control
0x18002cd63  lea     rcx, WPP_GLOBAL_Control
0x18002cd6a  cmp     rbx, rcx
0x18002cd6d  jz      loc_18002CE44
0x18002cd73  test    byte ptr [rbx+1Ch], 10h
0x18002cd77  jz      loc_18002CE44
0x18002cd7d  mov     rbx, [rbx+10h]
0x18002cd81  call    cs:__imp_GetLastError
0x18002cd87  mov     edx, 88h
0x18002cd8c  mov     r9d, eax
0x18002cd8f  lea     r8, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids
0x18002cd96  mov     rcx, rbx
0x18002cd99  call    WPP_SF_d
0x18002cd9e  jmp     loc_18002CE44
0x18002cda3  mov     rcx, [rsp+38h+TokenHandle]
0x18002cda8  lea     rax, [rsp+38h+arg_8]
0x18002cdad  mov     [rsp+38h+var_10], rax
0x18002cdb2  xor     r9d, r9d
0x18002cdb5  xor     r8d, r8d
0x18002cdb8  mov     [rsp+38h+var_18], 1
0x18002cdc0  xor     edx, edx
0x18002cdc2  call    cs:__imp_GetGPOListInternalW
0x18002cdc8  mov     edi, eax
0x18002cdca  test    eax, eax
0x18002cdcc  jnz     short loc_18002CDF8
0x18002cdce  mov     rbx, cs:WPP_GLOBAL_Control
0x18002cdd5  lea     rcx, WPP_GLOBAL_Control
0x18002cddc  cmp     rbx, rcx
0x18002cddf  jz      short loc_18002CE44
0x18002cde1  test    byte ptr [rbx+1Ch], 10h
0x18002cde5  jz      short loc_18002CE44
0x18002cde7  mov     rbx, [rbx+10h]
0x18002cdeb  call    cs:__imp_GetLastError
0x18002cdf1  mov     edx, 89h
0x18002cdf6  jmp     short loc_18002CD8C
0x18002cdf8  mov     rcx, [rsp+38h+arg_8]
0x18002cdfd  mov     r9d, 1
0x18002ce03  mov     r8d, esi
0x18002ce06  jmp     short loc_18002CE3C
0x18002ce08  lea     rdx, [rcx+20h]
0x18002ce0c  mov     r10d, esi
0x18002ce0f  test    rdx, rdx
0x18002ce12  jz      short loc_18002CE25
0x18002ce14  cmp     [rdx], si
0x18002ce17  jz      short loc_18002CE25
0x18002ce19  movzx   eax, word ptr [rdx]
0x18002ce1c  add     r10d, eax
0x18002ce1f  add     rdx, 2
0x18002ce23  jnz     short loc_18002CE14
0x18002ce25  mov     eax, [rcx+4]
0x18002ce28  mov     rcx, [rcx+90h]
0x18002ce2f  add     eax, r10d
0x18002ce32  imul    eax, r9d
0x18002ce36  add     r8d, eax
0x18002ce39  inc     r9d
0x18002ce3c  test    rcx, rcx
0x18002ce3f  jnz     short loc_18002CE08
0x18002ce41  mov     [rbx], r8d
0x18002ce44  mov     rcx, [rsp+38h+arg_8]
0x18002ce49  test    rcx, rcx
0x18002ce4c  jz      short loc_18002CE54
0x18002ce4e  call    cs:__imp_FreeGPOListInternalW
0x18002ce54  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x18002ce59  call    cs:__imp_CloseHandle
0x18002ce5f  mov     rbx, [rsp+38h+arg_0]
0x18002ce64  mov     eax, edi
0x18002ce66  mov     rsi, [rsp+38h+arg_18]
0x18002ce6b  add     rsp, 30h
0x18002ce6f  pop     rdi
0x18002ce70  retn
```
