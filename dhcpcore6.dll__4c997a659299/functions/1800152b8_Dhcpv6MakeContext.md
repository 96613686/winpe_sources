# Dhcpv6MakeContext

- ea: `0x1800152b8`
- end: `0x180015645`
- name: `Dhcpv6MakeContext`
- size: `909`
- prototype: `__int64 __fastcall(_QWORD *, __int64 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x180014e18`

## callees

- `0x180007564`
- `0x18000c740`
- `0x18000e21c`
- `0x18000ee8c`
- `0x1800128dc`
- `0x1800152b8`
- `0x18001564c`
- `0x180018d74`
- `0x18001a3ee`
- `0x18003098c`
- `0x1800338c0`
- `0x180033de4`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180015313`
- `ntdll!RtlNtStatusToDosError` at `0x180015313`
- `ntdll!RtlFreeUnicodeString` at `0x1800153da`
- `ntdll!RtlFreeUnicodeString` at `0x1800153da`
- `ntdll!RtlStringFromGUID` at `0x180015305`
- `ntdll!RtlStringFromGUID` at `0x180015305`
- `RPCRT4!UuidCreate` at `0x18001560b`
- `RPCRT4!UuidCreate` at `0x18001560b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015354`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015354`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800155a4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800155a4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800155c1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800155c1`

## pseudocode

```c
__int64 __fastcall Dhcpv6MakeContext(_QWORD *a1, __int64 *a2)
{
  __int64 v3; // rbx
  unsigned int LinkCharacteristics; // edi
  NTSTATUS v6; // eax
  __int64 v7; // rdi
  void *v8; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  int v12; // ecx
  __int64 v13; // rcx
  __int64 v14; // rdx
  _BYTE *v15; // rax
  _BYTE *v16; // rax
  unsigned int v17; // eax
  LPVOID v18; // [rsp+20h] [rbp-20h] BYREF
  struct _UNICODE_STRING GuidString; // [rsp+28h] [rbp-18h] BYREF
  char *v20; // [rsp+80h] [rbp+40h] BYREF
  HKEY hKey; // [rsp+88h] [rbp+48h] BYREF

  hKey = 0;
  v3 = 0;
  v20 = 0;
  v18 = 0;
  GuidString = 0;
  LinkCharacteristics = Dhcpv6GetLinkCharacteristics(a1, &v20);
  if ( !LinkCharacteristics )
  {
    v6 = RtlStringFromGUID((const GUID *const)(v20 + 12), &GuidString);
    LinkCharacteristics = RtlNtStatusToDosError(v6);
    if ( !LinkCharacteristics )
    {
      v7 = (unsigned int)GuidString.Length + 2;
      v8 = (void *)DhcpAlloc(9160);
      v18 = v8;
      v3 = (__int64)v8;
      if ( v8
        && (memset_0(v8, 0, 0x23C8u), v10 = DhcpAlloc(*((unsigned __int16 *)v20 + 28)),
                                      (*(_QWORD *)(v3 + 80) = v10) != 0)
        && (v11 = DhcpAlloc(v7), (*(_QWORD *)(v3 + 56) = v11) != 0) )
      {
        *(_DWORD *)(v3 + 16) = 1;
        *(_QWORD *)(v3 + 24) = *a1;
        *(_DWORD *)(v3 + 48) = *((_DWORD *)v20 + 2);
        *(_OWORD *)(v3 + 32) = *(_OWORD *)(v20 + 12);
        *(_DWORD *)(v3 + 92) = *((_DWORD *)v20 + 10);
        *(_DWORD *)(v3 + 96) = *((_DWORD *)v20 + 11);
        *(_BYTE *)(v3 + 8948) = v20[72];
        *(_BYTE *)(v3 + 76) = v20[36];
        *(_DWORD *)(v3 + 88) = *((unsigned __int16 *)v20 + 28);
        memcpy_0(*(void **)(v3 + 80), *((const void **)v20 + 8), *((unsigned __int16 *)v20 + 28));
        if ( !g_fVelocityDhcpnsiv6StyleUpdate )
          *(_DWORD *)(v3 + 572) = 0;
        v12 = *((_DWORD *)v20 + 8);
        if ( g_fVelocityDhcpv6ContextBitfieldUpdate )
          *(_DWORD *)(v3 + 8896) = v12;
        else
          *(_DWORD *)(v3 + 8860) ^= ((unsigned __int16)*(_DWORD *)(v3 + 8860)
                                   ^ (unsigned __int16)((_WORD)v12 << 11))
                                  & 0x800;
        memcpy_0(*(void **)(v3 + 56), GuidString.Buffer, GuidString.Length);
        *(_WORD *)(*(_QWORD *)(v3 + 56) + 2 * ((unsigned __int64)GuidString.Length >> 1)) = 0;
        *(_QWORD *)(v3 + 64) = -1;
        *(_DWORD *)(v3 + 9052) = 0;
        *(_DWORD *)(v3 + 9032) = IsHardwareAddressRandomized(*(_QWORD *)(v3 + 80), *(_QWORD *)(v3 + 56));
        *(_QWORD *)(v3 + 9040) = 0;
        *(_DWORD *)(v3 + 9048) = 0;
        LinkCharacteristics = Dhcpv6CreateAdapterKey(*(LPCWSTR *)(v3 + 56), &hKey);
        if ( !LinkCharacteristics )
        {
          v13 = 16;
          *(_QWORD *)(v3 + 648) = hKey;
          v14 = 16;
          v15 = (_BYTE *)(v3 + 456);
          do
          {
            *v15++ = 0;
            --v14;
          }
          while ( v14 );
          v16 = (_BYTE *)(v3 + 480);
          do
          {
            *v16++ = 0;
            --v13;
          }
          while ( v13 );
          if ( *(_DWORD *)(v3 + 9032) )
          {
            InitializeDUIDLL(v3);
LABEL_37:
            if ( !g_fVelocityDhcpnsiv6StyleUpdate )
            {
              if ( (xmmword_1800423E0 & 2) != 0 )
                WPP_SF_D(1025, 57, WPP_642d1a2b547f3a6a91393fb9cb453e87_Traceguids, 50);
              LinkCharacteristics = 0;
            }
            v17 = UuidCreate((UUID *)(v3 + 9136));
            if ( v17 && (xmmword_1800423E0 & 2) != 0 )
              WPP_SF_d(1025, 34, WPP_80912ccc52483efd9cc4ca3c8a600041_Traceguids, v17);
            *a2 = v3;
            goto LABEL_17;
          }
          EnterCriticalSection(&Dhcpv6GlobalDuidAccessCritSect);
          LinkCharacteristics = Dhcpv6ReadWriteClientDUID(v3);
          LeaveCriticalSection(&Dhcpv6GlobalDuidAccessCritSect);
          if ( !LinkCharacteristics )
            goto LABEL_37;
        }
      }
      else
      {
        LinkCharacteristics = 8;
      }
    }
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( v3 )
  {
    if ( *(_QWORD *)(v3 + 456) )
      DhcpFree((LPVOID *)(v3 + 456));
    if ( *(_QWORD *)(v3 + 80) )
      DhcpFree((LPVOID *)(v3 + 80));
    if ( *(_QWORD *)(v3 + 56) )
      DhcpFree((LPVOID *)(v3 + 56));
    DhcpFree(&v18);
  }
  if ( (xmmword_1800423E0 & 2) != 0 )
    WPP_SF_D(1025, 35, WPP_80912ccc52483efd9cc4ca3c8a600041_Traceguids, LinkCharacteristics);
LABEL_17:
  if ( v20 )
    DhcpFree((LPVOID *)&v20);
  if ( GuidString.Buffer )
    RtlFreeUnicodeString(&GuidString);
  return LinkCharacteristics;
}

```

## disassembly

```asm
0x1800152b8  mov     [rsp-28h+arg_0], rbx
0x1800152bd  push    rbp
0x1800152be  push    rsi
0x1800152bf  push    rdi
0x1800152c0  push    r14
0x1800152c2  push    r15
0x1800152c4  mov     rbp, rsp
0x1800152c7  sub     rsp, 40h
0x1800152cb  xor     r15d, r15d
0x1800152ce  mov     r14, rdx
0x1800152d1  xorps   xmm0, xmm0
0x1800152d4  mov     [rbp+hKey], r15
0x1800152d8  mov     ebx, r15d
0x1800152db  mov     [rbp+arg_10], r15
0x1800152df  lea     rdx, [rbp+arg_10]
0x1800152e3  mov     [rbp+var_20], rbx
0x1800152e7  mov     rsi, rcx
0x1800152ea  movups  xmmword ptr [rbp+GuidString.Length], xmm0
0x1800152ee  call    Dhcpv6GetLinkCharacteristics
0x1800152f3  mov     edi, eax
0x1800152f5  test    eax, eax
0x1800152f7  jnz     short loc_18001534B
0x1800152f9  mov     rcx, [rbp+arg_10]
0x1800152fd  lea     rdx, [rbp+GuidString]; GuidString
0x180015301  add     rcx, 0Ch; Guid
0x180015305  call    cs:__imp_RtlStringFromGUID
0x18001530c  nop     dword ptr [rax+rax+00h]
0x180015311  mov     ecx, eax; Status
0x180015313  call    cs:__imp_RtlNtStatusToDosError
0x18001531a  nop     dword ptr [rax+rax+00h]
0x18001531f  mov     edi, eax
0x180015321  test    eax, eax
0x180015323  jnz     short loc_18001534B
0x180015325  movzx   edi, [rbp+GuidString.Length]
0x180015329  mov     ecx, 23C8h
0x18001532e  add     edi, 2
0x180015331  call    DhcpAlloc
0x180015336  mov     [rbp+var_20], rax
0x18001533a  mov     rbx, rax
0x18001533d  test    rax, rax
0x180015340  jnz     loc_1800153FA
0x180015346  mov     edi, 8
0x18001534b  mov     rcx, [rbp+hKey]; hKey
0x18001534f  test    rcx, rcx
0x180015352  jz      short loc_180015364
0x180015354  call    cs:__imp_RegCloseKey
0x18001535b  nop     dword ptr [rax+rax+00h]
0x180015360  mov     [rbp+hKey], r15
0x180015364  test    rbx, rbx
0x180015367  jz      short loc_18001539F
0x180015369  lea     rcx, [rbx+1C8h]
0x180015370  cmp     [rcx], r15
0x180015373  jz      short loc_18001537A
0x180015375  call    DhcpFree
0x18001537a  lea     rcx, [rbx+50h]
0x18001537e  cmp     [rcx], r15
0x180015381  jz      short loc_180015388
0x180015383  call    DhcpFree
0x180015388  lea     rcx, [rbx+38h]
0x18001538c  cmp     [rcx], r15
0x18001538f  jz      short loc_180015396
0x180015391  call    DhcpFree
0x180015396  lea     rcx, [rbp+var_20]
0x18001539a  call    DhcpFree
0x18001539f  test    byte ptr cs:xmmword_1800423E0, 2
0x1800153a6  jz      short loc_1800153C1
0x1800153a8  mov     edx, 23h ; '#'
0x1800153ad  lea     r8, WPP_80912ccc52483efd9cc4ca3c8a600041_Traceguids
0x1800153b4  mov     ecx, 401h
0x1800153b9  mov     r9d, edi
0x1800153bc  call    WPP_SF_D
0x1800153c1  cmp     [rbp+arg_10], r15
0x1800153c5  jz      short loc_1800153D0
0x1800153c7  lea     rcx, [rbp+arg_10]
0x1800153cb  call    DhcpFree
0x1800153d0  cmp     [rbp+GuidString.Buffer], r15
0x1800153d4  jz      short loc_1800153E6
0x1800153d6  lea     rcx, [rbp+GuidString]; UnicodeString
0x1800153da  call    cs:__imp_RtlFreeUnicodeString
0x1800153e1  nop     dword ptr [rax+rax+00h]
0x1800153e6  mov     rbx, [rsp+40h+arg_0]
0x1800153eb  mov     eax, edi
0x1800153ed  add     rsp, 40h
0x1800153f1  pop     r15
0x1800153f3  pop     r14
0x1800153f5  pop     rdi
0x1800153f6  pop     rsi
0x1800153f7  pop     rbp
0x1800153f8  retn
0x1800153fa  xor     edx, edx; Val
0x1800153fc  mov     r8d, 23C8h; Size
0x180015402  mov     rcx, rbx; void *
0x180015405  call    memset_0
0x18001540a  mov     rax, [rbp+arg_10]
0x18001540e  movzx   ecx, word ptr [rax+38h]
0x180015412  call    DhcpAlloc
0x180015417  mov     [rbx+50h], rax
0x18001541b  test    rax, rax
0x18001541e  jz      loc_180015346
0x180015424  mov     rcx, rdi
0x180015427  call    DhcpAlloc
0x18001542c  mov     [rbx+38h], rax
0x180015430  test    rax, rax
0x180015433  jz      loc_180015346
0x180015439  mov     dword ptr [rbx+10h], 1
0x180015440  mov     rax, [rsi]
0x180015443  mov     [rbx+18h], rax
0x180015447  mov     rax, [rbp+arg_10]
0x18001544b  mov     ecx, [rax+8]
0x18001544e  mov     [rbx+30h], ecx
0x180015451  mov     rax, [rbp+arg_10]
0x180015455  movups  xmm0, xmmword ptr [rax+0Ch]
0x180015459  movdqu  xmmword ptr [rbx+20h], xmm0
0x18001545e  mov     rax, [rbp+arg_10]
0x180015462  mov     ecx, [rax+28h]
0x180015465  mov     [rbx+5Ch], ecx
0x180015468  mov     rax, [rbp+arg_10]
0x18001546c  mov     ecx, [rax+2Ch]
0x18001546f  mov     [rbx+60h], ecx
0x180015472  mov     rax, [rbp+arg_10]
0x180015476  mov     cl, [rax+48h]
0x180015479  mov     [rbx+22F4h], cl
0x18001547f  mov     rax, [rbp+arg_10]
0x180015483  mov     cl, [rax+24h]
0x180015486  mov     [rbx+4Ch], cl
0x180015489  mov     rax, [rbp+arg_10]
0x18001548d  movzx   ecx, word ptr [rax+38h]
0x180015491  mov     [rbx+58h], ecx
0x180015494  mov     rdx, [rbp+arg_10]
0x180015498  mov     rcx, [rbx+50h]; void *
0x18001549c  movzx   r8d, word ptr [rdx+38h]; Size
0x1800154a1  mov     rdx, [rdx+40h]; Src
0x1800154a5  call    memcpy_0
0x1800154aa  cmp     cs:g_fVelocityDhcpnsiv6StyleUpdate, r15d
0x1800154b1  jnz     short loc_1800154BA
0x1800154b3  mov     [rbx+23Ch], r15d
0x1800154ba  cmp     cs:g_fVelocityDhcpv6ContextBitfieldUpdate, r15d
0x1800154c1  mov     rax, [rbp+arg_10]
0x1800154c5  mov     ecx, [rax+20h]
0x1800154c8  jz      short loc_1800154D2
0x1800154ca  mov     [rbx+22C0h], ecx
0x1800154d0  jmp     short loc_1800154EB
0x1800154d2  mov     edx, [rbx+229Ch]
0x1800154d8  shl     ecx, 0Bh
0x1800154db  xor     ecx, edx
0x1800154dd  and     ecx, 800h
0x1800154e3  xor     ecx, edx
0x1800154e5  mov     [rbx+229Ch], ecx
0x1800154eb  movzx   r8d, [rbp+GuidString.Length]; Size
0x1800154f0  mov     rdx, [rbp+GuidString.Buffer]; Src
0x1800154f4  mov     rcx, [rbx+38h]; void *
0x1800154f8  call    memcpy_0
0x1800154fd  movzx   edx, [rbp+GuidString.Length]
0x180015501  mov     rcx, [rbx+38h]
0x180015505  shr     rdx, 1
0x180015508  mov     [rcx+rdx*2], r15w
0x18001550d  mov     qword ptr [rbx+40h], 0FFFFFFFFFFFFFFFFh
0x180015515  mov     [rbx+235Ch], r15d
0x18001551c  mov     rdx, [rbx+38h]
0x180015520  mov     rcx, [rbx+50h]
0x180015524  call    IsHardwareAddressRandomized
0x180015529  mov     [rbx+2348h], eax
0x18001552f  lea     rdx, [rbp+hKey]; phkResult
0x180015533  mov     [rbx+2350h], r15
0x18001553a  mov     [rbx+2358h], r15d
0x180015541  mov     rcx, [rbx+38h]; lpSubKey
0x180015545  call    Dhcpv6CreateAdapterKey
0x18001554a  mov     edi, eax
0x18001554c  test    eax, eax
0x18001554e  jnz     loc_18001534B
0x180015554  mov     rax, [rbp+hKey]
0x180015558  lea     ecx, [rdi+10h]
0x18001555b  mov     [rbx+288h], rax
0x180015562  mov     edx, ecx
0x180015564  lea     rax, [rbx+1C8h]
0x18001556b  mov     [rax], r15b
0x18001556e  inc     rax
0x180015571  sub     rdx, 1
0x180015575  jnz     short loc_18001556B
0x180015577  lea     rax, [rbx+1E0h]
0x18001557e  mov     [rax], r15b
0x180015581  inc     rax
0x180015584  sub     rcx, 1
0x180015588  jnz     short loc_18001557E
0x18001558a  cmp     [rbx+2348h], r15d
0x180015591  jz      short loc_18001559D
0x180015593  mov     rcx, rbx
0x180015596  call    InitializeDUIDLL
0x18001559b  jmp     short loc_1800155D5
0x18001559d  lea     rcx, Dhcpv6GlobalDuidAccessCritSect; lpCriticalSection
0x1800155a4  call    cs:__imp_EnterCriticalSection
0x1800155ab  nop     dword ptr [rax+rax+00h]
0x1800155b0  mov     rcx, rbx
0x1800155b3  call    Dhcpv6ReadWriteClientDUID
0x1800155b8  lea     rcx, Dhcpv6GlobalDuidAccessCritSect; lpCriticalSection
0x1800155bf  mov     edi, eax
0x1800155c1  call    cs:__imp_LeaveCriticalSection
0x1800155c8  nop     dword ptr [rax+rax+00h]
0x1800155cd  test    edi, edi
0x1800155cf  jnz     loc_18001534B
0x1800155d5  cmp     cs:g_fVelocityDhcpnsiv6StyleUpdate, r15d
0x1800155dc  jnz     short loc_180015604
0x1800155de  test    byte ptr cs:xmmword_1800423E0, 2
0x1800155e5  jz      short loc_180015601
0x1800155e7  mov     edx, 39h ; '9'
0x1800155ec  lea     r8, WPP_642d1a2b547f3a6a91393fb9cb453e87_Traceguids
0x1800155f3  mov     ecx, 401h
0x1800155f8  lea     r9d, [rdx-7]
0x1800155fc  call    WPP_SF_D
0x180015601  mov     edi, r15d
0x180015604  lea     rcx, [rbx+23B0h]; Uuid
0x18001560b  call    cs:__imp_UuidCreate
0x180015612  nop     dword ptr [rax+rax+00h]
0x180015617  test    eax, eax
0x180015619  jz      short loc_18001563D
0x18001561b  test    byte ptr cs:xmmword_1800423E0, 2
0x180015622  jz      short loc_18001563D
0x180015624  mov     edx, 22h ; '"'
0x180015629  lea     r8, WPP_80912ccc52483efd9cc4ca3c8a600041_Traceguids
0x180015630  mov     ecx, 401h
0x180015635  mov     r9d, eax
0x180015638  call    WPP_SF_d
0x18001563d  mov     [r14], rbx
0x180015640  jmp     loc_1800153C1
```
