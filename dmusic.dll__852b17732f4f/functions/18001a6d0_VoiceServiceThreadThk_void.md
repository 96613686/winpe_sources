# VoiceServiceThreadThk(void *)

- ea: `0x18001a6d0`
- end: `0x18001a7cd`
- name: `?VoiceServiceThreadThk@@YAKPEAX@Z`
- size: `253`
- prototype: `DWORD __stdcall(LPVOID lpThreadParameter)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x18001a114`
- `0x18001a6d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001a7a7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001a7a7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a747`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a798`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a747`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a798`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a71e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a730`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a71e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a730`

## pseudocode

```c
__int64 __fastcall VoiceServiceThreadThk(LPVOID lpThreadParameter)
{
  DWORD v1; // ebx
  bool v2; // di
  char v3; // si
  _QWORD *v4; // rdx
  unsigned int v5; // ebx
  __int64 i; // rax
  unsigned int v7; // eax
  __int64 v8; // rcx
  __int64 v9; // rax
  __int64 v10; // r8
  DWORD v11; // eax
  bool v13; // [rsp+38h] [rbp+10h] BYREF

  v1 = 500;
  while ( 1 )
  {
    v11 = WaitForSingleObject(CDirectMusicVoice::m_hVSTWakeUp, v1);
    if ( CDirectMusicVoice::m_fVSTStopping )
      return 0;
    v2 = 0;
    v13 = 0;
    if ( v11 )
    {
      if ( v11 == 258 )
      {
        v3 = 1;
        goto LABEL_7;
      }
    }
    else
    {
      v3 = 0;
      if ( !CDirectMusicVoice::m_fVSTStopping )
      {
        v2 = 1;
        v13 = 1;
        v3 = 1;
      }
LABEL_7:
      EnterCriticalSection(&CDirectMusicVoice::m_csVST);
      if ( v3 )
      {
        EnterCriticalSection(&CDirectMusicVoice::m_csVST);
        CDirectMusicVoice::ServiceVoiceQueue(&v13);
        LeaveCriticalSection(&CDirectMusicVoice::m_csVST);
        v2 = v13;
      }
      if ( v2 )
      {
        v4 = (_QWORD *)CDirectMusicVoice::m_ClientList;
        v5 = -1;
        while ( v4 )
        {
          for ( i = v4[2]; ; i = *(_QWORD *)(v10 + 8) )
          {
            v8 = i - 8;
            v9 = -i;
            v10 = v8 & -(__int64)(v9 != 0);
            if ( !v10 )
              break;
            v7 = *(_DWORD *)((v8 & -(__int64)(v9 != 0)) + 0x58);
            if ( v5 < v7 )
              v7 = v5;
            v5 = v7;
          }
          v4 = (_QWORD *)*v4;
        }
        v1 = v5 >> 1;
      }
      LeaveCriticalSection(&CDirectMusicVoice::m_csVST);
    }
  }
}

```

## disassembly

```asm
0x18001a6d0  mov     [rsp+arg_0], rbx
0x18001a6d5  mov     [rsp+arg_10], rsi
0x18001a6da  push    rdi
0x18001a6db  sub     rsp, 20h
0x18001a6df  mov     ebx, 1F4h
0x18001a6e4  jmp     loc_18001A79E
0x18001a6e9  xor     dil, dil
0x18001a6ec  mov     [rsp+28h+arg_8], dil
0x18001a6f1  test    eax, eax
0x18001a6f3  jz      short loc_18001A705
0x18001a6f5  cmp     eax, 102h
0x18001a6fa  jnz     loc_18001A79E
0x18001a700  mov     sil, 1
0x18001a703  jmp     short loc_18001A717
0x18001a705  xor     sil, sil
0x18001a708  test    cl, cl
0x18001a70a  jnz     short loc_18001A717
0x18001a70c  mov     dil, 1
0x18001a70f  mov     [rsp+28h+arg_8], dil
0x18001a714  mov     sil, dil
0x18001a717  lea     rcx, ?m_csVST@CDirectMusicVoice@@2U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001a71e  call    cs:__imp_EnterCriticalSection
0x18001a724  test    sil, sil
0x18001a727  jz      short loc_18001A752
0x18001a729  lea     rcx, ?m_csVST@CDirectMusicVoice@@2U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001a730  call    cs:__imp_EnterCriticalSection
0x18001a736  lea     rcx, [rsp+28h+arg_8]; bool *
0x18001a73b  call    ?ServiceVoiceQueue@CDirectMusicVoice@@CAXPEA_N@Z; CDirectMusicVoice::ServiceVoiceQueue(bool *)
0x18001a740  lea     rcx, ?m_csVST@CDirectMusicVoice@@2U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001a747  call    cs:__imp_LeaveCriticalSection
0x18001a74d  mov     dil, [rsp+28h+arg_8]
0x18001a752  test    dil, dil
0x18001a755  jz      short loc_18001A791
0x18001a757  mov     rdx, cs:?m_ClientList@CDirectMusicVoice@@0VCVSTClientList@@A; CVSTClientList CDirectMusicVoice::m_ClientList
0x18001a75e  or      ebx, 0FFFFFFFFh
0x18001a761  jmp     short loc_18001A78A
0x18001a763  mov     rax, [rdx+10h]
0x18001a767  jmp     short loc_18001A778
0x18001a769  mov     eax, [r8+58h]
0x18001a76d  cmp     ebx, eax
0x18001a76f  cmovb   eax, ebx
0x18001a772  mov     ebx, eax
0x18001a774  mov     rax, [r8+8]
0x18001a778  lea     rcx, [rax-8]
0x18001a77c  neg     rax
0x18001a77f  sbb     r8, r8
0x18001a782  and     r8, rcx
0x18001a785  jnz     short loc_18001A769
0x18001a787  mov     rdx, [rdx]
0x18001a78a  test    rdx, rdx
0x18001a78d  jnz     short loc_18001A763
0x18001a78f  shr     ebx, 1
0x18001a791  lea     rcx, ?m_csVST@CDirectMusicVoice@@2U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001a798  call    cs:__imp_LeaveCriticalSection
0x18001a79e  mov     rcx, cs:?m_hVSTWakeUp@CDirectMusicVoice@@0PEAXEA; hHandle
0x18001a7a5  mov     edx, ebx; dwMilliseconds
0x18001a7a7  call    cs:__imp_WaitForSingleObject
0x18001a7ad  mov     cl, cs:?m_fVSTStopping@CDirectMusicVoice@@0_NA; bool CDirectMusicVoice::m_fVSTStopping
0x18001a7b3  test    cl, cl
0x18001a7b5  jz      loc_18001A6E9
0x18001a7bb  mov     rbx, [rsp+28h+arg_0]
0x18001a7c0  xor     eax, eax
0x18001a7c2  mov     rsi, [rsp+28h+arg_10]
0x18001a7c7  add     rsp, 20h
0x18001a7cb  pop     rdi
0x18001a7cc  retn
```
