# DeleteCredentialsFromCredMan

- ea: `0x1800531ac`
- end: `0x180053330`
- name: `DeleteCredentialsFromCredMan`
- size: `388`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180055174`

## callees

- `0x180005bcc`
- `0x180005bfc`
- `0x18004236c`
- `0x1800531ac`

## import_xrefs

- `api-ms-win-security-credentials-l1-1-0!CredDeleteA` at `0x180053295`
- `api-ms-win-security-credentials-l1-1-0!CredDeleteA` at `0x1800532af`
- `api-ms-win-security-credentials-l1-1-0!CredDeleteA` at `0x180053295`
- `api-ms-win-security-credentials-l1-1-0!CredDeleteA` at `0x1800532af`
- `api-ms-win-security-credentials-l1-1-0!CredDeleteW` at `0x180053266`
- `api-ms-win-security-credentials-l1-1-0!CredDeleteW` at `0x180053280`
- `api-ms-win-security-credentials-l1-1-0!CredDeleteW` at `0x180053266`
- `api-ms-win-security-credentials-l1-1-0!CredDeleteW` at `0x180053280`

## pseudocode

```c
__int64 __fastcall DeleteCredentialsFromCredMan(__int64 a1)
{
  struct _LIST_ENTRY *v2; // rcx
  unsigned int v3; // edi
  __int64 UserData; // rax

  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 138, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids);
    v2 = WPP_GLOBAL_Control;
  }
  v3 = 0;
  if ( (*(_DWORD *)(a1 + 112) & 0x20) != 0 )
  {
    UserData = GetUserData(a1 + 32, 6);
    if ( UserData && *(_DWORD *)(UserData + 20) >= 0xC28u )
    {
      if ( (*(_BYTE *)(UserData + 24) & 8) != 0 )
      {
        CredDeleteW(L"*Session", 3u, 0);
        CredDeleteW(L"*Session", 2u, 0);
      }
      else
      {
        CredDeleteA("*Session", 3u, 0);
        CredDeleteA("*Session", 2u, 0);
      }
      *(_DWORD *)(a1 + 112) &= ~0x20u;
    }
    else
    {
      v3 = 1168;
      v2 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        return v3;
      if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0 || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
        goto LABEL_21;
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 140, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids, 1168);
    }
    goto LABEL_20;
  }
  if ( v2 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
    return v3;
  if ( (HIDWORD(v2[1].Blink) & 0x2000) != 0 && BYTE1(v2[1].Blink) >= 5u )
  {
    WPP_SF_(v2[1].Flink, 139, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids);
LABEL_20:
    v2 = WPP_GLOBAL_Control;
  }
LABEL_21:
  if ( v2 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(v2[1].Blink) & 0x2000) != 0
    && BYTE1(v2[1].Blink) >= 6u )
  {
    WPP_SF_d(v2[1].Flink, 141, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids, v3);
  }
  return v3;
}

```

## disassembly

```asm
0x1800531ac  push    rbx
0x1800531ae  push    rbp
0x1800531af  push    rsi
0x1800531b0  push    rdi
0x1800531b1  sub     rsp, 28h
0x1800531b5  mov     rbx, rcx
0x1800531b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800531bf  lea     rbp, WPP_GLOBAL_Control
0x1800531c6  mov     esi, 2000h
0x1800531cb  cmp     rcx, rbp
0x1800531ce  jz      short loc_1800531F7
0x1800531d0  test    [rcx+1Ch], esi
0x1800531d3  jz      short loc_1800531F7
0x1800531d5  cmp     byte ptr [rcx+19h], 6
0x1800531d9  jb      short loc_1800531F7
0x1800531db  mov     rcx, [rcx+10h]
0x1800531df  lea     r8, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids
0x1800531e6  mov     edx, 8Ah
0x1800531eb  call    WPP_SF_
0x1800531f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800531f7  mov     eax, [rbx+70h]
0x1800531fa  xor     edi, edi
0x1800531fc  test    al, 20h
0x1800531fe  jnz     short loc_180053236
0x180053200  cmp     rcx, rbp
0x180053203  jz      loc_180053324
0x180053209  test    [rcx+1Ch], esi
0x18005320c  jz      loc_1800532FC
0x180053212  cmp     byte ptr [rcx+19h], 5
0x180053216  jb      loc_1800532FC
0x18005321c  mov     rcx, [rcx+10h]
0x180053220  lea     r8, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids
0x180053227  mov     edx, 8Bh
0x18005322c  call    WPP_SF_
0x180053231  jmp     loc_1800532F5
0x180053236  lea     rcx, [rbx+20h]
0x18005323a  mov     edx, 6
0x18005323f  call    GetUserData
0x180053244  test    rax, rax
0x180053247  jz      short loc_1800532C1
0x180053249  cmp     dword ptr [rax+14h], 0C28h
0x180053250  jb      short loc_1800532C1
0x180053252  xor     r8d, r8d; Flags
0x180053255  test    byte ptr [rax+18h], 8
0x180053259  lea     edx, [r8+3]; Type
0x18005325d  jz      short loc_18005328E
0x18005325f  lea     rcx, TargetName; "*Session"
0x180053266  call    cs:__imp_CredDeleteW
0x18005326d  nop     dword ptr [rax+rax+00h]
0x180053272  xor     r8d, r8d; Flags
0x180053275  lea     rcx, TargetName; "*Session"
0x18005327c  lea     edx, [r8+2]; Type
0x180053280  call    cs:__imp_CredDeleteW
0x180053287  nop     dword ptr [rax+rax+00h]
0x18005328c  jmp     short loc_1800532BB
0x18005328e  lea     rcx, aSession_0; "*Session"
0x180053295  call    cs:__imp_CredDeleteA
0x18005329c  nop     dword ptr [rax+rax+00h]
0x1800532a1  xor     r8d, r8d; Flags
0x1800532a4  lea     rcx, aSession_0; "*Session"
0x1800532ab  lea     edx, [r8+2]; Type
0x1800532af  call    cs:__imp_CredDeleteA
0x1800532b6  nop     dword ptr [rax+rax+00h]
0x1800532bb  and     dword ptr [rbx+70h], 0FFFFFFDFh
0x1800532bf  jmp     short loc_1800532F5
0x1800532c1  mov     edi, 490h
0x1800532c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800532cd  cmp     rcx, rbp
0x1800532d0  jz      short loc_180053324
0x1800532d2  test    [rcx+1Ch], esi
0x1800532d5  jz      short loc_1800532FC
0x1800532d7  cmp     byte ptr [rcx+19h], 2
0x1800532db  jb      short loc_1800532FC
0x1800532dd  mov     rcx, [rcx+10h]
0x1800532e1  lea     r8, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids
0x1800532e8  mov     edx, 8Ch
0x1800532ed  mov     r9d, edi
0x1800532f0  call    WPP_SF_d
0x1800532f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800532fc  cmp     rcx, rbp
0x1800532ff  jz      short loc_180053324
0x180053301  test    [rcx+1Ch], esi
0x180053304  jz      short loc_180053324
0x180053306  cmp     byte ptr [rcx+19h], 6
0x18005330a  jb      short loc_180053324
0x18005330c  mov     rcx, [rcx+10h]
0x180053310  lea     r8, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids
0x180053317  mov     edx, 8Dh
0x18005331c  mov     r9d, edi
0x18005331f  call    WPP_SF_d
0x180053324  mov     eax, edi
0x180053326  add     rsp, 28h
0x18005332a  pop     rdi
0x18005332b  pop     rsi
0x18005332c  pop     rbp
0x18005332d  pop     rbx
0x18005332e  retn
```
