# midiSeqMessage

- ea: `0x180005270`
- end: `0x180005800`
- name: `midiSeqMessage`
- size: `1424`
- prototype: `__int64 __fastcall(DWORD_PTR dwUser, DWORD_PTR, __int64, int *)`
- caller_count: `14`
- callee_count: `12`
- tags: `installer_update`

## callers

- `0x18000145c`
- `0x18000160c`
- `0x180001810`
- `0x180001a44`
- `0x180001bfc`
- `0x180001eec`
- `0x18000240c`
- `0x1800025fc`
- `0x180002a90`
- `0x180002eac`
- `0x180003520`
- `0x1800036e0`
- `0x1800038ac`
- `0x180005a1c`

## callees

- `0x180003ad4`
- `0x180003bb8`
- `0x180003d28`
- `0x18000484c`
- `0x180004c5c`
- `0x180004de8`
- `0x180004ef0`
- `0x180004ff8`
- `0x180005270`
- `0x18000583c`
- `0x180005a1c`
- `0x180005e2c`

## import_xrefs

- `api-ms-win-mm-time-l1-1-0!timeBeginPeriod` at `0x180005501`
- `api-ms-win-mm-time-l1-1-0!timeBeginPeriod` at `0x180005501`
- `api-ms-win-mm-time-l1-1-0!timeGetTime` at `0x180005434`
- `api-ms-win-mm-time-l1-1-0!timeGetTime` at `0x1800054e6`
- `api-ms-win-mm-time-l1-1-0!timeGetTime` at `0x180005434`
- `api-ms-win-mm-time-l1-1-0!timeGetTime` at `0x1800054e6`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x180005709`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x18000575e`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x180005709`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x18000575e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000546c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000546c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005444`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005444`
- `WINMM!midiOutUnprepareHeader` at `0x1800057a3`
- `WINMM!midiOutUnprepareHeader` at `0x1800057a3`
- `WINMM!midiOutClose` at `0x180005578`
- `WINMM!midiOutClose` at `0x1800057d6`
- `WINMM!midiOutClose` at `0x180005578`
- `WINMM!midiOutClose` at `0x1800057d6`
- `WINMM!midiOutOpen` at `0x180005559`
- `WINMM!midiOutOpen` at `0x180005559`
- `WINMM!midiOutPrepareHeader` at `0x1800055a3`
- `WINMM!midiOutPrepareHeader` at `0x1800055a3`

## pseudocode

```c
__int64 __fastcall midiSeqMessage(DWORD_PTR dwUser, DWORD_PTR a2, __int64 a3, __int64 *a4)
{
  __int64 v5; // rdi
  int v7; // edx
  int v8; // edx
  int v9; // edx
  int v10; // edx
  int v11; // edx
  int v12; // edx
  int v13; // edx
  int v14; // edx
  __int64 v15; // rax
  __int64 result; // rax
  unsigned int v17; // eax
  unsigned int v18; // eax
  unsigned __int64 v19; // rax
  DWORD Time; // eax
  HMIDIOUT *v21; // rsi
  unsigned int v22; // edi
  __int64 v23; // rbp
  __int64 v24; // rdi
  bool v25; // zf
  int v26; // ecx
  __int64 v27; // r8
  __int64 v28; // rax
  int *v29; // rdx
  int *v30; // rax
  __int64 v31; // rax
  int v32; // ebx
  int v33; // ecx
  __int64 v34; // rax
  _DWORD *v35; // rbx
  _DWORD *v36; // rax
  __int64 v37; // rax
  DWORD_PTR v38; // rbp
  __int64 i; // rsi
  HMIDIOUT v40; // rsi

  v5 = a3;
  if ( (_DWORD)a2 == 1 )
  {
    LODWORD(result) = CreateSequence(a3, a4);
    return (unsigned int)result;
  }
  if ( !dwUser )
    return 99;
  if ( (unsigned int)a2 > 0xC )
  {
    switch ( (_DWORD)a2 )
    {
      case 0xD:
        if ( *(_QWORD *)(dwUser + 168) )
        {
          v38 = dwUser + 988;
          for ( i = 0; i != 3; ++i )
            midiOutUnprepareHeader(*(HMIDIOUT *)(dwUser + 168), (LPMIDIHDR)(v38 + 368 * i), 0x70u);
          v40 = *(HMIDIOUT *)(dwUser + 168);
          *(_QWORD *)(dwUser + 168) = 0;
          if ( (_DWORD)v5 )
            AllNotesOff(dwUser, v40);
          midiOutClose(v40);
        }
        return 0;
      case 0xE:
        v34 = *(&arrayOfLists + 2 * *(unsigned int *)(dwUser + 188) + 1);
        if ( v34 )
        {
          v35 = 0;
          v36 = (_DWORD *)(v34 + 16);
          if ( v36 )
          {
            do
            {
              if ( *v36 > (unsigned int)a3 )
                break;
              v35 = v36;
              v37 = *((_QWORD *)v36 - 2);
              if ( !v37 )
                break;
              v36 = (_DWORD *)(v37 + 16);
            }
            while ( v36 );
            if ( v35 )
            {
              v33 = MulDiv(a3 - *v35, 1000, v35[2]) + v35[1];
              goto LABEL_102;
            }
          }
        }
        break;
      case 0xF:
        v28 = *(&arrayOfLists + 2 * *(unsigned int *)(dwUser + 188) + 1);
        if ( v28 )
        {
          v29 = 0;
          v30 = (int *)(v28 + 16);
          if ( v30 )
          {
            do
            {
              if ( v30[1] > (unsigned int)a3 )
                break;
              v29 = v30;
              v31 = *((_QWORD *)v30 - 2);
              if ( !v31 )
                break;
              v30 = (int *)(v31 + 16);
            }
            while ( v30 );
            if ( v29 )
            {
              v32 = *v29;
              v33 = v32 + MulDiv(a3 - v29[1], v29[2], 1000);
LABEL_102:
              *(_DWORD *)a4 = v33;
              return 0;
            }
          }
        }
        break;
      default:
        switch ( (_DWORD)a2 )
        {
          case 0x10:
            *(_DWORD *)(dwUser + 184) = 16;
            break;
          case 0x11:
            break;
          case 0x12:
            if ( (_WORD)a3 )
            {
              if ( (unsigned __int16)a3 != 1 )
              {
                v26 = (unsigned __int16)a3 - 2;
                v25 = (unsigned __int16)a3 == 2;
LABEL_74:
                if ( v25 || v26 != 2 )
                  return 106;
                *(_QWORD *)(dwUser + 44) = *a4;
                *(_DWORD *)(dwUser + 52) = *((_DWORD *)a4 + 2);
                return 0;
              }
              v27 = 1;
            }
            else
            {
              v27 = 0;
            }
            SetBit(dwUser + 140, 81, v27);
            *(_WORD *)(dwUser + 132) = v5;
            return 0;
          case 0x13:
            if ( !(_WORD)a3 )
            {
              *(_WORD *)(dwUser + 134) = 0;
              return 0;
            }
            v26 = (unsigned __int16)a3 - 2;
            v25 = (unsigned __int16)a3 == 2;
            goto LABEL_74;
          case 0x14:
            return *(_DWORD *)(dwUser + 2096) & 2;
          case 0x15:
            return *(_QWORD *)(dwUser + 168);
          default:
            return 105;
        }
        *(_DWORD *)(dwUser + 36) = a3;
LABEL_40:
        SeekTicks(dwUser, a2);
        return 0;
    }
    v33 = -1;
    goto LABEL_102;
  }
  if ( (_DWORD)a2 == 12 )
  {
    v21 = (HMIDIOUT *)(dwUser + 168);
    LODWORD(result) = midiOutOpen((LPHMIDIOUT)(dwUser + 168), a3, (DWORD_PTR)MIDICallback, 0, 0x30000u);
    if ( (_DWORD)result )
      return (unsigned int)result;
    v22 = SendPatchCache(dwUser);
    if ( v22 )
    {
      midiOutClose(*v21);
      result = v22;
      *v21 = 0;
      return result;
    }
    v23 = 0;
    v24 = 0;
    do
    {
      midiOutPrepareHeader(*v21, (LPMIDIHDR)(v24 + dwUser + 988), 0x70u);
      *(_DWORD *)(dwUser + v24 + 1012) |= 1u;
      ++v23;
      v24 += 368;
    }
    while ( v23 != 3 );
    return 0;
  }
  v7 = a2 - 2;
  if ( !v7 )
  {
    Destroy(dwUser);
    return 0;
  }
  v8 = v7 - 1;
  if ( !v8 )
  {
    *(_DWORD *)(dwUser + 184) = 3;
    if ( (_DWORD)a3 == -1 )
      LODWORD(v5) = *(_DWORD *)(dwUser + 16);
    if ( *(_DWORD *)(dwUser + 24) > *(_DWORD *)(dwUser + 16) )
    {
      LODWORD(result) = 97;
      return (unsigned int)result;
    }
    if ( *(_DWORD *)(dwUser + 8) )
    {
      if ( *(_DWORD *)(dwUser + 12) == (_DWORD)v5 )
        goto LABEL_52;
      Stop(dwUser);
    }
    *(_DWORD *)(dwUser + 8) = 1;
    Time = timeGetTime();
    v25 = *(_DWORD *)(dwUser + 192) == 0;
    *(_DWORD *)(dwUser + 28) = Time;
    *(_DWORD *)(dwUser + 12) = v5;
    if ( v25 )
    {
      timeBeginPeriod(MINPERIOD);
      *(_DWORD *)(dwUser + 192) = 1;
    }
    if ( *(_DWORD *)(dwUser + 20) )
    {
      LODWORD(result) = SetTimerCallback(dwUser, MINPERIOD);
      return (unsigned int)result;
    }
LABEL_52:
    LODWORD(result) = 0;
    return (unsigned int)result;
  }
  v9 = v8 - 1;
  if ( !v9 )
  {
    v5 = 0;
LABEL_36:
    a2 = dwUser;
    if ( *(_DWORD *)dwUser )
      LODWORD(v19) = *(_DWORD *)(dwUser + 4) * v5;
    else
      v19 = (unsigned __int64)(v5 * *(int *)(dwUser + 4)) >> 2;
    *(_DWORD *)(dwUser + 36) = v19;
    goto LABEL_40;
  }
  v10 = v9 - 2;
  if ( !v10 )
  {
    if ( !(_DWORD)a3 )
      return 282;
    v17 = 60000000;
    if ( *(_DWORD *)dwUser )
      v17 = 1000000;
    v18 = v17 / (*(_DWORD *)(dwUser + 4) * (int)a3);
    if ( !v18 )
      v18 = 1;
    v25 = *(_DWORD *)(dwUser + 160) == 0;
    *(_DWORD *)(dwUser + 40) = v18;
    if ( !v25 )
    {
      DestroyTimer(dwUser, 0);
      *(_DWORD *)(dwUser + 28) = timeGetTime();
      EnterCriticalSection(&CritSec);
      if ( *(_DWORD *)(dwUser + 8) )
        SetTimerCallback(dwUser, MINPERIOD);
      LeaveCriticalSection(&CritSec);
    }
    return 0;
  }
  v11 = v10 - 1;
  if ( !v11 )
    goto LABEL_36;
  v12 = v11 - 1;
  if ( !v12 )
  {
    if ( !(unsigned int)SetUpToPlay() )
    {
      Destroy(dwUser);
      return 100;
    }
    return 0;
  }
  v13 = v12 - 1;
  if ( !v13 )
  {
    Stop(dwUser);
    return 0;
  }
  v14 = v13 - 1;
  if ( v14 )
  {
    if ( v14 == 1 )
    {
      if ( a3 )
      {
        *(_WORD *)a3 = *(_WORD *)dwUser;
        *(_WORD *)(a3 + 2) = *(_WORD *)(dwUser + 4);
        *(_DWORD *)(a3 + 4) = *(_DWORD *)(dwUser + 16);
        *(_DWORD *)(a3 + 8) = *(_DWORD *)(dwUser + 8);
        *(_DWORD *)(a3 + 12) = *(_DWORD *)(dwUser + 36) != -1;
        *(_DWORD *)(a3 + 16) = *(_DWORD *)(dwUser + 20);
        *(_DWORD *)(a3 + 20) = *(_DWORD *)(dwUser + 24);
        *(_DWORD *)(a3 + 24) = *(_DWORD *)(dwUser + 12);
        *(_DWORD *)(a3 + 28) = *(_DWORD *)(dwUser + 40);
        *(_QWORD *)(a3 + 36) = *(_QWORD *)(dwUser + 44);
        *(_DWORD *)(a3 + 44) = *(_DWORD *)(dwUser + 52);
        *(_WORD *)(a3 + 48) = *(_WORD *)(dwUser + 132);
        *(_WORD *)(a3 + 50) = *(_WORD *)(dwUser + 134);
        *(_BYTE *)(a3 + 53) = *(_BYTE *)(dwUser + 2096) & 1;
        v15 = *(&arrayOfLists + 2 * *(unsigned int *)(dwUser + 188) + 1);
        *(_BYTE *)(a3 + 52) = v15 && v15 != -16;
        return 0;
      }
      return 106;
    }
    return 105;
  }
  if ( !a3 )
    return 106;
  LODWORD(result) = NewTrackData(dwUser, a3);
  return (unsigned int)result;
}

```

## disassembly

```asm
0x180005270  push    rbx
0x180005272  push    rbp
0x180005273  push    rsi
0x180005274  push    rdi
0x180005275  push    r15
0x180005277  sub     rsp, 30h
0x18000527b  mov     r15d, 1
0x180005281  mov     rsi, r9
0x180005284  mov     rdi, r8
0x180005287  mov     rbx, rcx
0x18000528a  cmp     edx, r15d
0x18000528d  jz      loc_1800057E8
0x180005293  test    rcx, rcx
0x180005296  jz      loc_1800057E1
0x18000529c  cmp     edx, 0Ch
0x18000529f  ja      loc_1800055C6
0x1800052a5  jz      loc_18000553B
0x1800052ab  sub     edx, 2
0x1800052ae  jz      loc_180005531
0x1800052b4  sub     edx, r15d
0x1800052b7  jz      loc_1800054A9
0x1800052bd  sub     edx, r15d
0x1800052c0  jz      loc_180005479
0x1800052c6  sub     edx, 2
0x1800052c9  jz      loc_1800053F7
0x1800052cf  sub     edx, r15d
0x1800052d2  jz      loc_18000547B
0x1800052d8  sub     edx, r15d
0x1800052db  jz      loc_1800053D8
0x1800052e1  sub     edx, r15d
0x1800052e4  jz      loc_1800053CE
0x1800052ea  sub     edx, r15d
0x1800052ed  jz      loc_1800053B8
0x1800052f3  cmp     edx, r15d
0x1800052f6  jnz     loc_180005609
0x1800052fc  test    r8, r8
0x1800052ff  jz      loc_180005643
0x180005305  movzx   eax, word ptr [rcx]
0x180005308  mov     [r8], ax
0x18000530c  movzx   eax, word ptr [rcx+4]
0x180005310  mov     [r8+2], ax
0x180005315  mov     eax, [rcx+10h]
0x180005318  mov     [r8+4], eax
0x18000531c  mov     eax, [rcx+8]
0x18000531f  or      ecx, 0FFFFFFFFh
0x180005322  mov     [r8+8], eax
0x180005326  xor     eax, eax
0x180005328  cmp     [rbx+24h], ecx
0x18000532b  lea     rcx, arrayOfLists; dwUser
0x180005332  setnz   al
0x180005335  mov     [r8+0Ch], eax
0x180005339  mov     eax, [rbx+14h]
0x18000533c  mov     [r8+10h], eax
0x180005340  mov     eax, [rbx+18h]
0x180005343  mov     [r8+14h], eax
0x180005347  mov     eax, [rbx+0Ch]
0x18000534a  mov     [r8+18h], eax
0x18000534e  mov     eax, [rbx+28h]
0x180005351  mov     [r8+1Ch], eax
0x180005355  movsd   xmm0, qword ptr [rbx+2Ch]
0x18000535a  movsd   qword ptr [r8+24h], xmm0
0x180005360  mov     eax, [rbx+34h]
0x180005363  mov     [r8+2Ch], eax
0x180005367  movzx   eax, word ptr [rbx+84h]
0x18000536e  mov     [r8+30h], ax
0x180005373  movzx   eax, word ptr [rbx+86h]
0x18000537a  mov     [r8+32h], ax
0x18000537f  mov     al, [rbx+830h]
0x180005385  and     al, r15b
0x180005388  mov     [r8+35h], al
0x18000538c  mov     eax, [rbx+0BCh]
0x180005392  add     rax, rax
0x180005395  mov     rax, [rcx+rax*8+8]
0x18000539a  test    rax, rax
0x18000539d  jz      short loc_1800053AE
0x18000539f  add     rax, 10h
0x1800053a3  jz      short loc_1800053AE
0x1800053a5  mov     [r8+34h], r15b
0x1800053a9  jmp     loc_180005472
0x1800053ae  mov     byte ptr [r8+34h], 0
0x1800053b3  jmp     loc_180005472
0x1800053b8  test    rdi, rdi
0x1800053bb  jz      loc_180005643
0x1800053c1  mov     rdx, rdi
0x1800053c4  call    NewTrackData
0x1800053c9  jmp     loc_1800057F3
0x1800053ce  call    Stop
0x1800053d3  jmp     loc_180005472
0x1800053d8  call    SetUpToPlay
0x1800053dd  test    eax, eax
0x1800053df  jnz     loc_180005472
0x1800053e5  mov     rcx, rbx
0x1800053e8  call    Destroy
0x1800053ed  mov     eax, 64h ; 'd'
0x1800053f2  jmp     loc_1800057F5
0x1800053f7  test    edi, edi
0x1800053f9  jnz     short loc_180005405
0x1800053fb  mov     eax, 11Ah
0x180005400  jmp     loc_1800057F5
0x180005405  imul    edi, [rcx+4]
0x180005409  xor     edx, edx
0x18000540b  mov     eax, 3938700h
0x180005410  cmp     [rcx], edx
0x180005412  jz      short loc_180005419
0x180005414  mov     eax, 0F4240h
0x180005419  div     edi
0x18000541b  test    eax, eax
0x18000541d  cmovz   eax, r15d
0x180005421  cmp     dword ptr [rcx+0A0h], 0
0x180005428  mov     [rcx+28h], eax
0x18000542b  jz      short loc_180005472
0x18000542d  xor     edx, edx
0x18000542f  call    DestroyTimer
0x180005434  call    cs:__imp_timeGetTime
0x18000543a  lea     rcx, CritSec; lpCriticalSection
0x180005441  mov     [rbx+1Ch], eax
0x180005444  call    cs:__imp_EnterCriticalSection
0x18000544a  cmp     dword ptr [rbx+8], 0
0x18000544e  jz      short loc_180005465
0x180005450  mov     r8d, [rbx+9Ch]
0x180005457  mov     rcx, rbx; dwUser
0x18000545a  mov     edx, cs:MINPERIOD; uDelay
0x180005460  call    SetTimerCallback
0x180005465  lea     rcx, CritSec; lpCriticalSection
0x18000546c  call    cs:__imp_LeaveCriticalSection
0x180005472  xor     eax, eax
0x180005474  jmp     loc_1800057F5
0x180005479  xor     edi, edi
0x18000547b  cmp     dword ptr [rcx], 0
0x18000547e  mov     rdx, rbx
0x180005481  jnz     short loc_180005491
0x180005483  movsxd  rax, dword ptr [rcx+4]
0x180005487  imul    rax, rdi
0x18000548b  shr     rax, 2
0x18000548f  jmp     short loc_180005497
0x180005491  imul    edi, [rcx+4]
0x180005495  mov     eax, edi
0x180005497  mov     ecx, 24h ; '$'
0x18000549c  mov     [rdx+rcx], eax
0x18000549f  mov     rcx, rbx
0x1800054a2  call    SeekTicks
0x1800054a7  jmp     short loc_180005472
0x1800054a9  mov     dword ptr [rcx+0B8h], 3
0x1800054b3  or      ecx, 0FFFFFFFFh
0x1800054b6  cmp     edi, ecx
0x1800054b8  jnz     short loc_1800054BD
0x1800054ba  mov     edi, [rbx+10h]
0x1800054bd  mov     eax, [rbx+10h]
0x1800054c0  cmp     [rbx+18h], eax
0x1800054c3  jbe     short loc_1800054CF
0x1800054c5  mov     eax, 61h ; 'a'
0x1800054ca  jmp     loc_1800057F3
0x1800054cf  cmp     dword ptr [rbx+8], 0
0x1800054d3  jz      short loc_1800054E2
0x1800054d5  cmp     [rbx+0Ch], edi
0x1800054d8  jz      short loc_18000552A
0x1800054da  mov     rcx, rbx
0x1800054dd  call    Stop
0x1800054e2  mov     [rbx+8], r15d
0x1800054e6  call    cs:__imp_timeGetTime
0x1800054ec  cmp     dword ptr [rbx+0C0h], 0
0x1800054f3  mov     [rbx+1Ch], eax
0x1800054f6  mov     [rbx+0Ch], edi
0x1800054f9  jnz     short loc_18000550E
0x1800054fb  mov     ecx, cs:MINPERIOD; uPeriod
0x180005501  call    cs:__imp_timeBeginPeriod
0x180005507  mov     [rbx+0C0h], r15d
0x18000550e  cmp     dword ptr [rbx+14h], 0
0x180005512  jz      short loc_18000552A
0x180005514  mov     edx, cs:MINPERIOD; uDelay
0x18000551a  xor     r8d, r8d
0x18000551d  mov     rcx, rbx; dwUser
0x180005520  call    SetTimerCallback
0x180005525  jmp     loc_1800057F3
0x18000552a  xor     eax, eax
0x18000552c  jmp     loc_1800057F3
0x180005531  call    Destroy
0x180005536  jmp     loc_180005472
0x18000553b  lea     rsi, [rcx+0A8h]
0x180005542  mov     [rsp+58h+fdwOpen], 30000h; fdwOpen
0x18000554a  mov     rcx, rsi; phmo
0x18000554d  lea     r8, MIDICallback; dwCallback
0x180005554  xor     r9d, r9d; dwInstance
0x180005557  mov     edx, edi; uDeviceID
0x180005559  call    cs:__imp_midiOutOpen
0x18000555f  test    eax, eax
0x180005561  jnz     loc_1800057F3
0x180005567  mov     rcx, rbx
0x18000556a  call    SendPatchCache
0x18000556f  mov     edi, eax
0x180005571  test    eax, eax
0x180005573  jz      short loc_18000558C
0x180005575  mov     rcx, [rsi]; hmo
0x180005578  call    cs:__imp_midiOutClose
0x18000557e  mov     eax, edi
0x180005580  mov     qword ptr [rsi], 0
0x180005587  jmp     loc_1800057F5
0x18000558c  xor     ebp, ebp
0x18000558e  xor     edi, edi
0x180005590  mov     rcx, [rsi]; hmo
0x180005593  lea     rdx, [rbx+3DCh]
0x18000559a  add     rdx, rdi; pmh
0x18000559d  mov     r8d, 70h ; 'p'; cbmh
0x1800055a3  call    cs:__imp_midiOutPrepareHeader
0x1800055a9  or      [rbx+rdi+3F4h], r15d
0x1800055b1  add     rbp, r15
0x1800055b4  add     rdi, 170h
0x1800055bb  cmp     rbp, 3
0x1800055bf  jnz     short loc_180005590
0x1800055c1  jmp     loc_180005472
0x1800055c6  mov     eax, edx
0x1800055c8  sub     eax, 0Dh
0x1800055cb  jz      loc_180005775
0x1800055d1  sub     eax, r15d
0x1800055d4  jz      loc_180005714
0x1800055da  sub     eax, r15d
0x1800055dd  jz      loc_1800056B3
0x1800055e3  sub     eax, r15d
0x1800055e6  jz      loc_1800056A5
0x1800055ec  sub     eax, r15d
0x1800055ef  jz      loc_1800056AB
0x1800055f5  sub     eax, r15d
0x1800055f8  jz      short loc_180005659
0x1800055fa  sub     eax, r15d
0x1800055fd  jz      short loc_18000562D
0x1800055ff  sub     eax, r15d
0x180005602  jz      short loc_18000561F
0x180005604  cmp     eax, r15d
0x180005607  jz      short loc_180005613
0x180005609  mov     eax, 69h ; 'i'
0x18000560e  jmp     loc_1800057F5
0x180005613  mov     rax, [rcx+0A8h]
0x18000561a  jmp     loc_1800057F5
0x18000561f  mov     eax, [rcx+830h]
0x180005625  and     eax, 2
0x180005628  jmp     loc_1800057F5
0x18000562d  movzx   ecx, di
0x180005630  test    ecx, ecx
0x180005632  jz      short loc_18000564D
0x180005634  sub     ecx, 2
0x180005637  jz      short loc_180005643
0x180005639  sub     ecx, r15d
0x18000563c  jz      short loc_180005643
0x18000563e  cmp     ecx, r15d
0x180005641  jz      short loc_18000566A
0x180005643  mov     eax, 6Ah ; 'j'
0x180005648  jmp     loc_1800057F5
0x18000564d  mov     [rbx+86h], di
0x180005654  jmp     loc_180005472
0x180005659  movzx   ecx, di
0x18000565c  test    ecx, ecx
0x18000565e  jz      short loc_180005685
0x180005660  sub     ecx, r15d
0x180005663  jz      short loc_180005680
0x180005665  sub     ecx, r15d
0x180005668  jmp     short loc_180005637
0x18000566a  movsd   xmm0, qword ptr [r9]
0x18000566f  movsd   qword ptr [rbx+2Ch], xmm0
0x180005674  mov     eax, [r9+8]
0x180005678  mov     [rbx+34h], eax
0x18000567b  jmp     loc_180005472
0x180005680  mov     r8d, r15d
0x180005683  jmp     short loc_180005688
0x180005685  xor     r8d, r8d
0x180005688  lea     rcx, [rbx+8Ch]
0x18000568f  mov     edx, 51h ; 'Q'
0x180005694  call    SetBit
0x180005699  mov     [rbx+84h], di
0x1800056a0  jmp     loc_180005472
0x1800056a5  mov     [rcx+0B8h], edx
0x1800056ab  mov     [rcx+24h], edi
0x1800056ae  jmp     loc_1800054A2
0x1800056b3  mov     eax, [rcx+0BCh]
0x1800056b9  lea     rcx, arrayOfLists
0x1800056c0  add     rax, rax
0x1800056c3  mov     rax, [rcx+rax*8+8]
0x1800056c8  test    rax, rax
0x1800056cb  jz      loc_18000576B
0x1800056d1  xor     edx, edx
0x1800056d3  add     rax, 10h
0x1800056d7  jz      loc_18000576B
0x1800056dd  cmp     [rax+4], edi
0x1800056e0  ja      short loc_1800056F4
0x1800056e2  mov     rdx, rax
0x1800056e5  mov     rax, [rax-10h]
0x1800056e9  test    rax, rax
0x1800056ec  jz      short loc_1800056F4
0x1800056ee  add     rax, 10h
0x1800056f2  jnz     short loc_1800056DD
0x1800056f4  test    rdx, rdx
0x1800056f7  jz      short loc_18000576B
0x1800056f9  sub     edi, [rdx+4]
0x1800056fc  mov     r8d, 3E8h; nDenominator
0x180005702  mov     ebx, [rdx]
0x180005704  mov     ecx, edi; nNumber
0x180005706  mov     edx, [rdx+8]; nNumerator
0x180005709  call    cs:__imp_MulDiv
0x18000570f  lea     ecx, [rbx+rax]
0x180005712  jmp     short loc_18000576E
0x180005714  mov     eax, [rcx+0BCh]
  ... truncated ...
```
