# IntfScanAndGetAvailableNetworks(_LAN_INTERFACE_CONTEXT *)

- ea: `0x18001ae7c`
- end: `0x18001b0a1`
- name: `?IntfScanAndGetAvailableNetworks@@YAKPEAU_LAN_INTERFACE_CONTEXT@@@Z`
- size: `549`
- prototype: `__int64 __fastcall(struct _LAN_INTERFACE_CONTEXT *)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180023760`

## callees

- `0x1800025f0`
- `0x180003114`
- `0x180008c38`
- `0x18000a7ec`
- `0x18000a87c`
- `0x18000a8f4`
- `0x18000a9c0`
- `0x18000c230`
- `0x18001ae7c`
- `0x1800280e0`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x18001af7d`
- `RPCRT4!UuidCreate` at `0x18001af7d`
- `dot3msm!Dot3MsmQueryMediaState` at `0x18001aec6`
- `dot3msm!Dot3MsmQueryMediaState` at `0x18001aec6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001af56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001af56`

## pseudocode

```c
__int64 __fastcall IntfScanAndGetAvailableNetworks(struct _LAN_INTERFACE_CONTEXT *a1)
{
  _DWORD *v2; // rsi
  DWORD MediaState; // ebx
  unsigned int v4; // eax
  __int64 v5; // rdx
  __int64 v6; // r8
  RPC_STATUS v7; // eax
  DWORD FriendlyNameFromGUID; // eax
  unsigned __int16 *v9; // rcx
  struct _LIST_ENTRY *v10; // rcx
  __int64 v11; // rdx
  void *v12; // rcx
  _DWORD v14[4]; // [rsp+20h] [rbp-258h] BYREF
  unsigned __int16 v15[264]; // [rsp+30h] [rbp-248h] BYREF

  v14[0] = 0;
  v2 = 0;
  memset_0(v15, 0, 0x202u);
  MediaState = Dot3MsmQueryMediaState(*((_QWORD *)a1 + 41), v14);
  if ( MediaState )
  {
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control[1].Blink)
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 148, WPP_0eee27c7e0cd3271439d8d336f664c32_Traceguids, MediaState);
    }
    goto LABEL_29;
  }
  if ( !v14[0] )
  {
    MediaState = 4308;
LABEL_29:
    Dot3Free(v2);
    return MediaState;
  }
  if ( !*((_QWORD *)a1 + 57) )
  {
    v4 = SafeVariableListBufferSize(0x248u, 0, 0x240u);
    v2 = Dot3Alloc(v4, v5, v6);
    if ( !v2 )
    {
      MediaState = GetLastError();
      if ( MediaState )
        goto LABEL_29;
    }
    *v2 = 1;
    v2[142] = 0;
    v7 = UuidCreate((UUID *)(v2 + 130));
    MediaState = v7;
    if ( v7 )
    {
      if ( v7 != 1824 )
        goto LABEL_29;
    }
    v2[143] = 7;
    *(_OWORD *)(v2 + 134) = *(_OWORD *)*((_QWORD *)a1 + 37);
    *(_OWORD *)(v2 + 138) = *(_OWORD *)((char *)a1 + 8);
    FriendlyNameFromGUID = IntfHlpGetFriendlyNameFromGUID((const struct _GUID *)((char *)a1 + 8), v15);
    v9 = (unsigned __int16 *)(v2 + 2);
    MediaState = FriendlyNameFromGUID;
    if ( FriendlyNameFromGUID )
    {
      if ( StringCchCopyW(v9, 0x100u, *((const unsigned __int16 **)a1 + 15)) < 0 )
      {
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          || !BYTE1(WPP_GLOBAL_Control[1].Blink)
          || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
        {
          goto LABEL_20;
        }
        v11 = 150;
        goto LABEL_19;
      }
    }
    else if ( StringCchCopyW(v9, 0x100u, v15) < 0 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || !BYTE1(WPP_GLOBAL_Control[1].Blink)
        || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
      {
        goto LABEL_20;
      }
      v11 = 149;
LABEL_19:
      WPP_SF_(v10[1].Flink, v11, WPP_0eee27c7e0cd3271439d8d336f664c32_Traceguids);
LABEL_20:
      MediaState = 13;
      goto LABEL_29;
    }
    v12 = (void *)*((_QWORD *)a1 + 57);
    if ( v12 )
      Dot3Free(v12);
    *((_DWORD *)a1 + 112) = 1;
    *((_QWORD *)a1 + 57) = v2;
    if ( MediaState )
      goto LABEL_29;
  }
  return MediaState;
}

```

## disassembly

```asm
0x18001ae7c  push    rbx
0x18001ae7e  push    rbp
0x18001ae7f  push    rsi
0x18001ae80  push    r14
0x18001ae82  sub     rsp, 258h
0x18001ae89  mov     rax, cs:__security_cookie
0x18001ae90  xor     rax, rsp
0x18001ae93  mov     [rsp+278h+var_38], rax
0x18001ae9b  mov     rbp, rcx
0x18001ae9e  mov     [rsp+278h+var_258], 0
0x18001aea6  lea     rcx, [rsp+278h+var_248]; void *
0x18001aeab  xor     edx, edx; Val
0x18001aead  mov     r8d, 202h; Size
0x18001aeb3  xor     esi, esi
0x18001aeb5  call    memset_0
0x18001aeba  mov     rcx, [rbp+148h]
0x18001aec1  lea     rdx, [rsp+278h+var_258]
0x18001aec6  call    cs:__imp_Dot3MsmQueryMediaState
0x18001aecc  mov     ebx, eax
0x18001aece  test    eax, eax
0x18001aed0  jz      short loc_18001AF1A
0x18001aed2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001aed9  lea     rax, WPP_GLOBAL_Control
0x18001aee0  cmp     rcx, rax
0x18001aee3  jz      loc_18001B07A
0x18001aee9  cmp     byte ptr [rcx+19h], 1
0x18001aeed  jb      loc_18001B07A
0x18001aef3  test    byte ptr [rcx+1Ch], 1
0x18001aef7  jz      loc_18001B07A
0x18001aefd  mov     rcx, [rcx+10h]
0x18001af01  lea     r8, WPP_0eee27c7e0cd3271439d8d336f664c32_Traceguids
0x18001af08  mov     edx, 94h
0x18001af0d  mov     r9d, ebx
0x18001af10  call    WPP_SF_d
0x18001af15  jmp     loc_18001B07A
0x18001af1a  cmp     [rsp+278h+var_258], esi
0x18001af1e  jnz     short loc_18001AF2A
0x18001af20  mov     ebx, 10D4h
0x18001af25  jmp     loc_18001B07A
0x18001af2a  cmp     [rbp+1C8h], rsi
0x18001af31  jnz     loc_18001B082
0x18001af37  mov     ecx, 248h; unsigned __int64
0x18001af3c  xor     edx, edx; unsigned __int64
0x18001af3e  lea     r8d, [rcx-8]; unsigned __int64
0x18001af42  call    ?SafeVariableListBufferSize@@YAK_K00@Z; SafeVariableListBufferSize(unsigned __int64,unsigned __int64,unsigned __int64)
0x18001af47  mov     ecx, eax; dwBytes
0x18001af49  call    ?Dot3Alloc@@YAPEAX_K@Z; Dot3Alloc(unsigned __int64)
0x18001af4e  mov     rsi, rax
0x18001af51  test    rax, rax
0x18001af54  jnz     short loc_18001AF66
0x18001af56  call    cs:__imp_GetLastError
0x18001af5c  mov     ebx, eax
0x18001af5e  test    eax, eax
0x18001af60  jnz     loc_18001B07A
0x18001af66  mov     dword ptr [rsi], 1
0x18001af6c  lea     rcx, [rsi+208h]; Uuid
0x18001af73  mov     dword ptr [rsi+238h], 0
0x18001af7d  call    cs:__imp_UuidCreate
0x18001af83  mov     ebx, eax
0x18001af85  test    eax, eax
0x18001af87  jz      short loc_18001AF94
0x18001af89  cmp     eax, 720h
0x18001af8e  jnz     loc_18001B07A
0x18001af94  mov     dword ptr [rsi+23Ch], 7
0x18001af9e  lea     rcx, [rbp+8]; struct _GUID *
0x18001afa2  mov     rax, [rbp+128h]
0x18001afa9  lea     rdx, [rsp+278h+var_248]; unsigned __int16 *
0x18001afae  movups  xmm0, xmmword ptr [rax]
0x18001afb1  movdqu  xmmword ptr [rsi+218h], xmm0
0x18001afb9  movups  xmm1, xmmword ptr [rcx]
0x18001afbc  movdqu  xmmword ptr [rsi+228h], xmm1
0x18001afc4  call    ?IntfHlpGetFriendlyNameFromGUID@@YAKPEBU_GUID@@PEAGK@Z; IntfHlpGetFriendlyNameFromGUID(_GUID const *,ushort *,ulong)
0x18001afc9  lea     rcx, [rsi+8]; unsigned __int16 *
0x18001afcd  mov     ebx, eax
0x18001afcf  mov     edx, 100h; unsigned __int64
0x18001afd4  test    eax, eax
0x18001afd6  jnz     short loc_18001B021
0x18001afd8  lea     r8, [rsp+278h+var_248]; unsigned __int16 *
0x18001afdd  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001afe2  test    eax, eax
0x18001afe4  jns     short loc_18001B054
0x18001afe6  mov     rcx, cs:WPP_GLOBAL_Control
0x18001afed  lea     rax, WPP_GLOBAL_Control
0x18001aff4  cmp     rcx, rax
0x18001aff7  jz      short loc_18001B01A
0x18001aff9  cmp     byte ptr [rcx+19h], 1
0x18001affd  jb      short loc_18001B01A
0x18001afff  test    byte ptr [rcx+1Ch], 1
0x18001b003  jz      short loc_18001B01A
0x18001b005  mov     edx, 95h
0x18001b00a  mov     rcx, [rcx+10h]
0x18001b00e  lea     r8, WPP_0eee27c7e0cd3271439d8d336f664c32_Traceguids
0x18001b015  call    WPP_SF_
0x18001b01a  mov     ebx, 0Dh
0x18001b01f  jmp     short loc_18001B07A
0x18001b021  mov     r8, [rbp+78h]; unsigned __int16 *
0x18001b025  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001b02a  test    eax, eax
0x18001b02c  jns     short loc_18001B054
0x18001b02e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b035  lea     rax, WPP_GLOBAL_Control
0x18001b03c  cmp     rcx, rax
0x18001b03f  jz      short loc_18001B01A
0x18001b041  cmp     byte ptr [rcx+19h], 1
0x18001b045  jb      short loc_18001B01A
0x18001b047  test    byte ptr [rcx+1Ch], 1
0x18001b04b  jz      short loc_18001B01A
0x18001b04d  mov     edx, 96h
0x18001b052  jmp     short loc_18001B00A
0x18001b054  mov     rcx, [rbp+1C8h]; lpMem
0x18001b05b  test    rcx, rcx
0x18001b05e  jz      short loc_18001B065
0x18001b060  call    ?Dot3Free@@YAXPEAX@Z; Dot3Free(void *)
0x18001b065  mov     dword ptr [rbp+1C0h], 1
0x18001b06f  mov     [rbp+1C8h], rsi
0x18001b076  test    ebx, ebx
0x18001b078  jz      short loc_18001B082
0x18001b07a  mov     rcx, rsi; lpMem
0x18001b07d  call    ?Dot3Free@@YAXPEAX@Z; Dot3Free(void *)
0x18001b082  mov     eax, ebx
0x18001b084  mov     rcx, [rsp+278h+var_38]
0x18001b08c  xor     rcx, rsp; StackCookie
0x18001b08f  call    __security_check_cookie
0x18001b094  add     rsp, 258h
0x18001b09b  pop     r14
0x18001b09d  pop     rsi
0x18001b09e  pop     rbp
0x18001b09f  pop     rbx
0x18001b0a0  retn
```
