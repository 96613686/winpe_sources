# NewTrackData

- ea: `0x180005a1c`
- end: `0x180005ca5`
- name: `NewTrackData`
- size: `649`
- prototype: `__int64 __fastcall(DWORD_PTR dwUser, __int64)`
- caller_count: `1`
- callee_count: `16`
- tags: `installer_update`

## callers

- `0x180005270`

## callees

- `0x1800013fc`
- `0x180003dc0`
- `0x180003e98`
- `0x180003fdc`
- `0x1800044f0`
- `0x180004588`
- `0x180004c5c`
- `0x180004cc0`
- `0x180004e20`
- `0x180004fa4`
- `0x180005270`
- `0x180005808`
- `0x180005a1c`
- `0x180005cd0`
- `0x180005d4c`
- `0x180005e2c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005a8b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005b8c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005a8b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005b8c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005a51`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005b57`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005a51`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005b57`

## pseudocode

```c
__int64 __fastcall NewTrackData(DWORD_PTR dwUser, __int64 a2)
{
  __int64 v4; // rbx
  __int64 v5; // rax
  int v6; // ecx
  int v7; // ecx
  int v8; // ecx
  int v9; // ecx
  int v10; // ecx
  int v11; // ebx
  DWORD_PTR v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // rdx
  int v15; // ecx
  int v16; // ecx
  int v17; // ecx
  int v18; // ecx

  v4 = *(_QWORD *)(*(_QWORD *)(dwUser + 976) + 8LL * *(unsigned __int16 *)(a2 + 14));
  if ( !v4 )
    return 0;
  EnterCriticalSection(&CritSec);
  *(_QWORD *)(a2 + 16) = 0;
  v5 = *(_QWORD *)(v4 + 48);
  if ( v5 )
  {
    while ( *(_QWORD *)(v5 + 16) )
      v5 = *(_QWORD *)(v5 + 16);
    *(_QWORD *)(v5 + 16) = a2;
  }
  else
  {
    *(_QWORD *)(v4 + 48) = a2;
    *(_QWORD *)(v4 + 24) = *(_QWORD *)a2;
    *(_QWORD *)(v4 + 32) = *(_QWORD *)a2 + *(unsigned int *)(a2 + 8) - 1LL;
  }
  LeaveCriticalSection(&CritSec);
  v6 = *(_DWORD *)v4;
  *(_DWORD *)v4 = 0;
  if ( v6 > 275 )
  {
    v15 = v6 - 276;
    if ( v15 )
    {
      v16 = v15 - 1;
      if ( v16 )
      {
        v17 = v16 - 1;
        if ( v17 )
        {
          v18 = v17 - 1;
          if ( v18 )
          {
            if ( v18 != 1 )
              return 0;
            SkipBytes(v4, *(_DWORD *)(v4 + 80));
            if ( *(_DWORD *)v4 )
            {
              *(_DWORD *)v4 = 280;
              return 0;
            }
            goto LABEL_12;
          }
          SkipBytes(v4, *(_DWORD *)(v4 + 80));
          if ( *(_DWORD *)v4 )
          {
            *(_DWORD *)v4 = 279;
            return 0;
          }
          goto LABEL_40;
        }
        SkipBytes(v4, *(_DWORD *)(v4 + 80));
        if ( *(_DWORD *)v4 )
        {
          *(_DWORD *)v4 = 278;
          return 0;
        }
      }
      else
      {
        HandleMetaEvent(dwUser, v4, 0);
      }
    }
    SeekUnblock(dwUser);
    return 0;
  }
  if ( v6 == 275 )
  {
    SendSysEx(dwUser);
    if ( *(_BYTE *)(dwUser + 2093) )
      return 0;
    goto LABEL_12;
  }
  v7 = v6 - 270;
  if ( !v7 )
  {
LABEL_12:
    PlayUnblock(dwUser, v4);
    return 0;
  }
  v8 = v7 - 1;
  if ( !v8 )
  {
    if ( !(unsigned int)AllTracksUnblocked(dwUser) )
      return 0;
    v13 = 0;
    goto LABEL_25;
  }
  v9 = v8 - 1;
  if ( !v9 )
  {
    FillInNextTrack(v4);
    if ( (unsigned int)AllTracksUnblocked(dwUser) )
    {
      *(_DWORD *)(dwUser + 20) = 1;
      SendPatchCache(dwUser);
      if ( *(_DWORD *)(dwUser + 36) != -1 )
      {
        v11 = *(_DWORD *)(dwUser + 8);
        *(_DWORD *)(dwUser + 8) = 0;
        midiSeqMessage(dwUser);
        *(_DWORD *)(dwUser + 8) = v11;
      }
      EnterCriticalSection(&CritSec);
      if ( (unsigned int)GetNextEvent(dwUser) == 256 && *(_DWORD *)(dwUser + 8) )
        SetTimerCallback(v12, MINPERIOD);
      LeaveCriticalSection(&CritSec);
    }
    return 0;
  }
  v10 = v9 - 1;
  if ( !v10 )
  {
LABEL_40:
    v13 = v4;
LABEL_25:
    if ( (unsigned int)ScanEarlyMetas((_DWORD *)dwUser, v13) )
    {
      if ( (unsigned int)AllTracksUnblocked(dwUser) )
      {
        ResetToBeginning(dwUser);
        SetBlockedTracksTo(dwUser, v14, 272);
      }
    }
    else
    {
      List_Destroy(*(unsigned int *)(dwUser + 188));
    }
    return 0;
  }
  if ( v10 == 1 )
  {
    HandleMetaEvent(dwUser, v4, 0);
    goto LABEL_12;
  }
  return 0;
}

```

## disassembly

```asm
0x180005a1c  mov     [rsp+arg_0], rbx
0x180005a21  mov     [rsp+arg_8], rsi
0x180005a26  push    rdi
0x180005a27  sub     rsp, 20h
0x180005a2b  movzx   r8d, word ptr [rdx+0Eh]
0x180005a30  mov     rsi, rdx
0x180005a33  mov     rax, [rcx+3D0h]
0x180005a3a  mov     rdi, rcx
0x180005a3d  mov     rbx, [rax+r8*8]
0x180005a41  test    rbx, rbx
0x180005a44  jz      loc_180005C93
0x180005a4a  lea     rcx, CritSec; lpCriticalSection
0x180005a51  call    cs:__imp_EnterCriticalSection
0x180005a57  mov     qword ptr [rsi+10h], 0
0x180005a5f  mov     rax, [rbx+30h]
0x180005a63  test    rax, rax
0x180005a66  jnz     loc_180005AF6
0x180005a6c  mov     [rbx+30h], rsi
0x180005a70  mov     rax, [rsi]
0x180005a73  mov     [rbx+18h], rax
0x180005a77  mov     ecx, [rsi+8]
0x180005a7a  dec     rcx
0x180005a7d  add     rcx, [rsi]
0x180005a80  mov     [rbx+20h], rcx
0x180005a84  lea     rcx, CritSec; lpCriticalSection
0x180005a8b  call    cs:__imp_LeaveCriticalSection
0x180005a91  mov     ecx, [rbx]
0x180005a93  mov     eax, 113h
0x180005a98  mov     dword ptr [rbx], 0
0x180005a9e  cmp     ecx, eax
0x180005aa0  jg      loc_180005C0A
0x180005aa6  jz      loc_180005BF0
0x180005aac  sub     ecx, 10Eh
0x180005ab2  jz      short loc_180005AE2
0x180005ab4  sub     ecx, 1
0x180005ab7  jz      loc_180005B97
0x180005abd  sub     ecx, 1
0x180005ac0  jz      short loc_180005B03
0x180005ac2  sub     ecx, 1
0x180005ac5  jz      loc_180005C5A
0x180005acb  cmp     ecx, 1
0x180005ace  jnz     loc_180005C93
0x180005ad4  xor     r8d, r8d
0x180005ad7  mov     rdx, rbx
0x180005ada  mov     rcx, rdi
0x180005add  call    HandleMetaEvent
0x180005ae2  mov     rdx, rbx
0x180005ae5  mov     rcx, rdi
0x180005ae8  call    PlayUnblock
0x180005aed  jmp     loc_180005C93
0x180005af2  mov     rax, [rax+10h]
0x180005af6  cmp     qword ptr [rax+10h], 0
0x180005afb  jnz     short loc_180005AF2
0x180005afd  mov     [rax+10h], rsi
0x180005b01  jmp     short loc_180005A84
0x180005b03  mov     rcx, rbx
0x180005b06  call    FillInNextTrack
0x180005b0b  mov     rcx, rdi
0x180005b0e  call    AllTracksUnblocked
0x180005b13  test    eax, eax
0x180005b15  jz      loc_180005C93
0x180005b1b  mov     rcx, rdi
0x180005b1e  mov     dword ptr [rdi+14h], 1
0x180005b25  call    SendPatchCache
0x180005b2a  cmp     dword ptr [rdi+24h], 0FFFFFFFFh
0x180005b2e  jz      short loc_180005B50
0x180005b30  mov     ebx, [rdi+8]
0x180005b33  xor     r9d, r9d
0x180005b36  mov     r8d, [rdi+24h]
0x180005b3a  mov     rcx, rdi; dwUser
0x180005b3d  mov     dword ptr [rdi+8], 0
0x180005b44  lea     edx, [r9+10h]
0x180005b48  call    midiSeqMessage
0x180005b4d  mov     [rdi+8], ebx
0x180005b50  lea     rcx, CritSec; lpCriticalSection
0x180005b57  call    cs:__imp_EnterCriticalSection
0x180005b5d  mov     rcx, rdi
0x180005b60  call    GetNextEvent
0x180005b65  cmp     eax, 100h
0x180005b6a  jnz     short loc_180005B85
0x180005b6c  cmp     dword ptr [rdi+8], 0
0x180005b70  jz      short loc_180005B85
0x180005b72  mov     r8, [rdi+50h]
0x180005b76  mov     edx, cs:MINPERIOD; uDelay
0x180005b7c  mov     r8d, [r8+4]
0x180005b80  call    SetTimerCallback
0x180005b85  lea     rcx, CritSec; lpCriticalSection
0x180005b8c  call    cs:__imp_LeaveCriticalSection
0x180005b92  jmp     loc_180005C93
0x180005b97  mov     rcx, rdi
0x180005b9a  call    AllTracksUnblocked
0x180005b9f  test    eax, eax
0x180005ba1  jz      loc_180005C93
0x180005ba7  xor     edx, edx
0x180005ba9  mov     rcx, rdi
0x180005bac  call    ScanEarlyMetas
0x180005bb1  test    eax, eax
0x180005bb3  jnz     short loc_180005BC5
0x180005bb5  mov     ecx, [rdi+0BCh]
0x180005bbb  call    List_Destroy
0x180005bc0  jmp     loc_180005C93
0x180005bc5  mov     rcx, rdi
0x180005bc8  call    AllTracksUnblocked
0x180005bcd  test    eax, eax
0x180005bcf  jz      loc_180005C93
0x180005bd5  mov     rcx, rdi
0x180005bd8  call    ResetToBeginning
0x180005bdd  mov     r8d, 110h
0x180005be3  mov     rcx, rdi
0x180005be6  call    SetBlockedTracksTo
0x180005beb  jmp     loc_180005C93
0x180005bf0  mov     rcx, rdi
0x180005bf3  call    SendSysEx
0x180005bf8  cmp     byte ptr [rdi+82Dh], 0
0x180005bff  jz      loc_180005AE2
0x180005c05  jmp     loc_180005C93
0x180005c0a  sub     ecx, 114h
0x180005c10  jz      short loc_180005C88
0x180005c12  sub     ecx, 1
0x180005c15  jz      short loc_180005C7A
0x180005c17  sub     ecx, 1
0x180005c1a  jz      short loc_180005C62
0x180005c1c  sub     ecx, 1
0x180005c1f  jz      short loc_180005C42
0x180005c21  cmp     ecx, 1
0x180005c24  jnz     short loc_180005C93
0x180005c26  mov     edx, [rbx+50h]
0x180005c29  mov     rcx, rbx
0x180005c2c  call    SkipBytes
0x180005c31  cmp     dword ptr [rbx], 0
0x180005c34  jz      loc_180005AE2
0x180005c3a  mov     dword ptr [rbx], 118h
0x180005c40  jmp     short loc_180005C93
0x180005c42  mov     edx, [rbx+50h]
0x180005c45  mov     rcx, rbx
0x180005c48  call    SkipBytes
0x180005c4d  cmp     dword ptr [rbx], 0
0x180005c50  jz      short loc_180005C5A
0x180005c52  mov     dword ptr [rbx], 117h
0x180005c58  jmp     short loc_180005C93
0x180005c5a  mov     rdx, rbx
0x180005c5d  jmp     loc_180005BA9
0x180005c62  mov     edx, [rbx+50h]
0x180005c65  mov     rcx, rbx
0x180005c68  call    SkipBytes
0x180005c6d  cmp     dword ptr [rbx], 0
0x180005c70  jz      short loc_180005C88
0x180005c72  mov     dword ptr [rbx], 116h
0x180005c78  jmp     short loc_180005C93
0x180005c7a  xor     r8d, r8d
0x180005c7d  mov     rdx, rbx
0x180005c80  mov     rcx, rdi
0x180005c83  call    HandleMetaEvent
0x180005c88  mov     rdx, rbx
0x180005c8b  mov     rcx, rdi; dwUser
0x180005c8e  call    SeekUnblock
0x180005c93  mov     rbx, [rsp+28h+arg_0]
0x180005c98  xor     eax, eax
0x180005c9a  mov     rsi, [rsp+28h+arg_8]
0x180005c9f  add     rsp, 20h
0x180005ca3  pop     rdi
0x180005ca4  retn
```
