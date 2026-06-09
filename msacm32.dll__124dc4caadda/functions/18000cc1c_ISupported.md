# ISupported

- ea: `0x18000cc1c`
- end: `0x18000cddf`
- name: `ISupported`
- size: `451`
- prototype: `__int64 __fastcall(HDRVR hDriver, LPCWAVEFORMATEX pwfx)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000c434`
- `0x18000c890`
- `0x18000cb04`

## callees

- `0x18000cc1c`

## import_xrefs

- `api-ms-win-mm-misc-l1-1-0!SendDriverMessage` at `0x18000ccc1`
- `api-ms-win-mm-misc-l1-1-0!SendDriverMessage` at `0x18000cd2b`
- `api-ms-win-mm-misc-l1-1-0!SendDriverMessage` at `0x18000ccc1`
- `api-ms-win-mm-misc-l1-1-0!SendDriverMessage` at `0x18000cd2b`
- `api-ms-win-mm-mme-l1-1-0!waveInOpen` at `0x18000cd57`
- `api-ms-win-mm-mme-l1-1-0!waveInOpen` at `0x18000cdca`
- `api-ms-win-mm-mme-l1-1-0!waveInOpen` at `0x18000cd57`
- `api-ms-win-mm-mme-l1-1-0!waveInOpen` at `0x18000cdca`
- `api-ms-win-mm-mme-l1-1-0!waveInGetNumDevs` at `0x18000cd06`
- `api-ms-win-mm-mme-l1-1-0!waveInGetNumDevs` at `0x18000cd06`
- `api-ms-win-mm-mme-l1-1-0!waveOutGetNumDevs` at `0x18000cc99`
- `api-ms-win-mm-mme-l1-1-0!waveOutGetNumDevs` at `0x18000cc99`
- `api-ms-win-mm-mme-l1-1-0!waveOutOpen` at `0x18000cc70`
- `api-ms-win-mm-mme-l1-1-0!waveOutOpen` at `0x18000ccf1`
- `api-ms-win-mm-mme-l1-1-0!waveOutOpen` at `0x18000cd9e`
- `api-ms-win-mm-mme-l1-1-0!waveOutOpen` at `0x18000cc70`
- `api-ms-win-mm-mme-l1-1-0!waveOutOpen` at `0x18000ccf1`
- `api-ms-win-mm-mme-l1-1-0!waveOutOpen` at `0x18000cd9e`

## pseudocode

```c
_BOOL8 __fastcall ISupported(HDRVR hDriver, LPCWAVEFORMATEX pwfx, int a3)
{
  int v3; // eax
  UINT v7; // edx
  int v8; // ebx
  UINT NumDevs; // r12d
  int v10; // ecx
  UINT v11; // edi
  UINT i; // edi
  UINT j; // ebx
  LPARAM lParam1; // [rsp+70h] [rbp+18h] BYREF

  v3 = a3 & 0x1000000;
  LODWORD(lParam1) = 0;
  if ( (a3 & 0x400000) != 0 )
  {
    v8 = 0xFFFF;
    if ( v3 )
    {
      NumDevs = waveOutGetNumDevs();
      if ( NumDevs )
      {
        LODWORD(lParam1) = 0xFFFF;
        v10 = 0xFFFF;
        if ( hDriver )
        {
          SendDriverMessage(hDriver, 0x4002u, (LPARAM)&lParam1, 0);
          v10 = lParam1;
        }
        if ( HIWORD(v10) )
        {
          if ( !waveOutOpen(0, (__int16)v10, pwfx, 0, 0, 3u) )
            return 1;
        }
        else
        {
          for ( i = 0; i < NumDevs; ++i )
          {
            if ( !waveOutOpen(0, i, pwfx, 0, 0, 3u) )
              return 1;
          }
        }
      }
    }
    if ( (a3 & 0x800000) == 0 )
      return 0;
    v11 = waveInGetNumDevs();
    if ( !v11 )
      return 0;
    LODWORD(lParam1) = 0xFFFF;
    if ( hDriver )
    {
      SendDriverMessage(hDriver, 0x4000u, (LPARAM)&lParam1, 0);
      v8 = lParam1;
    }
    if ( !HIWORD(v8) )
    {
      for ( j = 0; j < v11; ++j )
      {
        if ( !waveInOpen(0, j, pwfx, 0, 0, 3u) )
          return 1;
      }
      return 0;
    }
    v7 = (__int16)v8;
  }
  else
  {
    if ( v3 && !waveOutOpen(0, 0xFFFFFFFF, pwfx, 0, 0, 3u) )
      return 1;
    if ( (a3 & 0x800000) == 0 )
      return 0;
    v7 = -1;
  }
  return !waveInOpen(0, v7, pwfx, 0, 0, 3u);
}

```

## disassembly

```asm
0x18000cc1c  mov     r11, rsp
0x18000cc1f  mov     [r11+8], rbx
0x18000cc23  mov     [r11+10h], rbp
0x18000cc27  push    rdi
0x18000cc28  push    r12
0x18000cc2a  push    r13
0x18000cc2c  push    r14
0x18000cc2e  push    r15
0x18000cc30  sub     rsp, 30h
0x18000cc34  xor     r13d, r13d
0x18000cc37  mov     eax, r8d
0x18000cc3a  and     eax, 1000000h
0x18000cc3f  mov     [r11+18h], r13d
0x18000cc43  mov     r14d, r8d
0x18000cc46  mov     r15, rdx
0x18000cc49  mov     rbp, rcx
0x18000cc4c  bt      r8d, 16h
0x18000cc51  jb      short loc_18000CC90
0x18000cc53  or      ebx, 0FFFFFFFFh
0x18000cc56  test    eax, eax
0x18000cc58  jz      short loc_18000CC7E
0x18000cc5a  mov     r8, rdx; pwfx
0x18000cc5d  mov     [rsp+58h+fdwOpen], 3; fdwOpen
0x18000cc65  mov     edx, ebx; uDeviceID
0x18000cc67  mov     [r11-38h], r13
0x18000cc6b  xor     r9d, r9d; dwCallback
0x18000cc6e  xor     ecx, ecx; phwo
0x18000cc70  call    cs:__imp_waveOutOpen
0x18000cc76  test    eax, eax
0x18000cc78  jz      loc_18000CDD8
0x18000cc7e  bt      r14d, 17h
0x18000cc83  jnb     loc_18000CD61
0x18000cc89  mov     edx, ebx
0x18000cc8b  jmp     loc_18000CD42
0x18000cc90  mov     ebx, 0FFFFh
0x18000cc95  test    eax, eax
0x18000cc97  jz      short loc_18000CCFF
0x18000cc99  call    cs:__imp_waveOutGetNumDevs
0x18000cc9f  mov     r12d, eax
0x18000cca2  test    eax, eax
0x18000cca4  jz      short loc_18000CCFF
0x18000cca6  mov     dword ptr [rsp+58h+lParam1], ebx
0x18000ccaa  mov     ecx, ebx
0x18000ccac  test    rbp, rbp
0x18000ccaf  jz      short loc_18000CCCB
0x18000ccb1  xor     r9d, r9d; lParam2
0x18000ccb4  lea     r8, [rsp+58h+lParam1]; lParam1
0x18000ccb9  mov     edx, 4002h; message
0x18000ccbe  mov     rcx, rbp; hDriver
0x18000ccc1  call    cs:__imp_SendDriverMessage
0x18000ccc7  mov     ecx, dword ptr [rsp+58h+lParam1]
0x18000cccb  mov     eax, ecx
0x18000cccd  shr     eax, 10h
0x18000ccd0  test    ax, ax
0x18000ccd3  jz      loc_18000CD7B
0x18000ccd9  movsx   edx, cx; uDeviceID
0x18000ccdc  xor     r9d, r9d; dwCallback
0x18000ccdf  xor     ecx, ecx; phwo
0x18000cce1  mov     [rsp+58h+fdwOpen], 3; fdwOpen
0x18000cce9  mov     r8, r15; pwfx
0x18000ccec  mov     [rsp+58h+dwInstance], r13; dwInstance
0x18000ccf1  call    cs:__imp_waveOutOpen
0x18000ccf7  test    eax, eax
0x18000ccf9  jz      loc_18000CDD8
0x18000ccff  bt      r14d, 17h
0x18000cd04  jnb     short loc_18000CD61
0x18000cd06  call    cs:__imp_waveInGetNumDevs
0x18000cd0c  mov     edi, eax
0x18000cd0e  test    eax, eax
0x18000cd10  jz      short loc_18000CD61
0x18000cd12  mov     dword ptr [rsp+58h+lParam1], ebx
0x18000cd16  test    rbp, rbp
0x18000cd19  jz      short loc_18000CD35
0x18000cd1b  xor     r9d, r9d; lParam2
0x18000cd1e  lea     r8, [rsp+58h+lParam1]; lParam1
0x18000cd23  mov     edx, 4000h; message
0x18000cd28  mov     rcx, rbp; hDriver
0x18000cd2b  call    cs:__imp_SendDriverMessage
0x18000cd31  mov     ebx, dword ptr [rsp+58h+lParam1]
0x18000cd35  mov     eax, ebx
0x18000cd37  shr     eax, 10h
0x18000cd3a  test    ax, ax
0x18000cd3d  jz      short loc_18000CDAC
0x18000cd3f  movsx   edx, bx; uDeviceID
0x18000cd42  mov     [rsp+58h+fdwOpen], 3; fdwOpen
0x18000cd4a  mov     r8, r15; pwfx
0x18000cd4d  xor     r9d, r9d; dwCallback
0x18000cd50  mov     [rsp+58h+dwInstance], r13; dwInstance
0x18000cd55  xor     ecx, ecx; phwi
0x18000cd57  call    cs:__imp_waveInOpen
0x18000cd5d  test    eax, eax
0x18000cd5f  jz      short loc_18000CDD8
0x18000cd61  xor     eax, eax
0x18000cd63  mov     rbx, [rsp+58h+arg_0]
0x18000cd68  mov     rbp, [rsp+58h+arg_8]
0x18000cd6d  add     rsp, 30h
0x18000cd71  pop     r15
0x18000cd73  pop     r14
0x18000cd75  pop     r13
0x18000cd77  pop     r12
0x18000cd79  pop     rdi
0x18000cd7a  retn
0x18000cd7b  mov     edi, r13d
0x18000cd7e  cmp     edi, r12d
0x18000cd81  jnb     loc_18000CCFF
0x18000cd87  mov     [rsp+58h+fdwOpen], 3; fdwOpen
0x18000cd8f  xor     r9d, r9d; dwCallback
0x18000cd92  mov     r8, r15; pwfx
0x18000cd95  mov     [rsp+58h+dwInstance], r13; dwInstance
0x18000cd9a  mov     edx, edi; uDeviceID
0x18000cd9c  xor     ecx, ecx; phwo
0x18000cd9e  call    cs:__imp_waveOutOpen
0x18000cda4  test    eax, eax
0x18000cda6  jz      short loc_18000CDD8
0x18000cda8  inc     edi
0x18000cdaa  jmp     short loc_18000CD7E
0x18000cdac  mov     ebx, r13d
0x18000cdaf  cmp     ebx, edi
0x18000cdb1  jnb     short loc_18000CD61
0x18000cdb3  mov     [rsp+58h+fdwOpen], 3; fdwOpen
0x18000cdbb  xor     r9d, r9d; dwCallback
0x18000cdbe  mov     r8, r15; pwfx
0x18000cdc1  mov     [rsp+58h+dwInstance], r13; dwInstance
0x18000cdc6  mov     edx, ebx; uDeviceID
0x18000cdc8  xor     ecx, ecx; phwi
0x18000cdca  call    cs:__imp_waveInOpen
0x18000cdd0  test    eax, eax
0x18000cdd2  jz      short loc_18000CDD8
0x18000cdd4  inc     ebx
0x18000cdd6  jmp     short loc_18000CDAF
0x18000cdd8  mov     eax, 1
0x18000cddd  jmp     short loc_18000CD63
```
