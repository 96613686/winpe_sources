# Dhcpv6ReadWriteClientDUID

- ea: `0x18001564c`
- end: `0x1800157eb`
- name: `Dhcpv6ReadWriteClientDUID`
- size: `415`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800152b8`

## callees

- `0x18000c740`
- `0x18000f918`
- `0x18001564c`
- `0x180016658`
- `0x18001d9d8`
- `0x18002a454`
- `0x18002a810`
- `0x1800311c4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001570c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001570c`

## pseudocode

```c
__int64 __fastcall Dhcpv6ReadWriteClientDUID(__int64 a1)
{
  int matched; // r12d
  int v3; // eax
  unsigned int v4; // edi
  __int64 v5; // rbx
  unsigned int v6; // esi
  unsigned int v7; // eax
  BYTE *v8; // r14
  DWORD v9; // r13d
  int v10; // edx
  BYTE *lpData[2]; // [rsp+50h] [rbp-10h] BYREF
  unsigned int v13; // [rsp+A8h] [rbp+48h] BYREF
  DWORD cbData; // [rsp+B0h] [rbp+50h] BYREF
  __int64 v15; // [rsp+B8h] [rbp+58h] BYREF

  v13 = 0;
  cbData = 0;
  v15 = 0;
  lpData[0] = 0;
  matched = 1;
  v3 = ReadClientDUID(a1, &v13, &v15);
  v4 = v13;
  v5 = v15;
  if ( v3 )
  {
    if ( !dword_180042510 && (unsigned int)Dhcpv6MatchDUIDTypes(v15, v13, 1) )
      matched = Dhcpv6MatchDUIDToNic(v5, v4);
    v6 = 0;
    if ( matched )
      goto LABEL_13;
  }
  v7 = Dhcpv6GenerateClientDUID(a1, &cbData, lpData);
  v8 = lpData[0];
  v6 = v7;
  if ( !v7 )
  {
    v9 = cbData;
    v6 = RegSetValueExW(Dhcpv6GlobalTcpipParametersKey, L"Dhcpv6DUID", 0, 3u, lpData[0], cbData);
    if ( !v6 )
    {
      if ( !matched )
      {
        if ( (Microsoft_Windows_DHCPv6_ClientEnableBits & 0x40) != 0 )
          McTemplateU0qbr0qbr2qbr4qbr6_EtwEventWriteTransfer(
            v9 - 8,
            v10,
            v4 - 8,
            v5 + 8,
            v4,
            v5,
            v9 - 8,
            (__int64)(v8 + 8),
            v9,
            (__int64)v8);
        DhcpFree(&v15);
      }
      LOWORD(v4) = v9;
      v5 = (__int64)v8;
LABEL_13:
      *(_DWORD *)(a1 + 464) = (unsigned __int16)v4;
      dword_180042510 = 1;
      *(_QWORD *)(a1 + 456) = v5;
      return v6;
    }
  }
  if ( v5 )
    DhcpFree(&v15);
  if ( v8 )
    DhcpFree(lpData);
  if ( (xmmword_1800423E0 & 2) != 0 )
    WPP_SF_dJ(1025, 29, WPP_80912ccc52483efd9cc4ca3c8a600041_Traceguids, v6, *(_QWORD *)(a1 + 24));
  return v6;
}

```

## disassembly

```asm
0x18001564c  mov     [rsp-38h+arg_0], rbx
0x180015651  push    rbp
0x180015652  push    rsi
0x180015653  push    rdi
0x180015654  push    r12
0x180015656  push    r13
0x180015658  push    r14
0x18001565a  push    r15
0x18001565c  mov     rbp, rsp
0x18001565f  sub     rsp, 60h
0x180015663  xor     r13d, r13d
0x180015666  lea     r8, [rbp+arg_18]
0x18001566a  lea     rdx, [rbp+arg_8]
0x18001566e  mov     [rbp+arg_8], r13d
0x180015672  mov     r15, rcx
0x180015675  mov     [rbp+arg_10], r13d
0x180015679  mov     [rbp+arg_18], r13
0x18001567d  lea     esi, [r13+1]
0x180015681  mov     [rbp+var_10], r13
0x180015685  mov     r12d, esi
0x180015688  call    ReadClientDUID
0x18001568d  mov     edi, [rbp+arg_8]
0x180015690  mov     rbx, [rbp+arg_18]
0x180015694  test    eax, eax
0x180015696  jz      short loc_1800156CB
0x180015698  cmp     cs:dword_180042510, r13d
0x18001569f  jnz     short loc_1800156BF
0x1800156a1  mov     r8d, esi
0x1800156a4  mov     edx, edi
0x1800156a6  mov     rcx, rbx
0x1800156a9  call    Dhcpv6MatchDUIDTypes
0x1800156ae  test    eax, eax
0x1800156b0  jz      short loc_1800156BF
0x1800156b2  mov     edx, edi
0x1800156b4  mov     rcx, rbx
0x1800156b7  call    Dhcpv6MatchDUIDToNic
0x1800156bc  mov     r12d, eax
0x1800156bf  mov     esi, r13d
0x1800156c2  test    r12d, r12d
0x1800156c5  jnz     loc_18001576C
0x1800156cb  lea     r8, [rbp+var_10]
0x1800156cf  mov     rcx, r15
0x1800156d2  lea     rdx, [rbp+arg_10]
0x1800156d6  call    Dhcpv6GenerateClientDUID
0x1800156db  mov     r14, [rbp+var_10]
0x1800156df  mov     esi, eax
0x1800156e1  test    eax, eax
0x1800156e3  jnz     loc_180015789
0x1800156e9  mov     r13d, [rbp+arg_10]
0x1800156ed  lea     r9d, [rax+3]; dwType
0x1800156f1  mov     rcx, cs:Dhcpv6GlobalTcpipParametersKey; hKey
0x1800156f8  lea     rdx, aDhcpv6duid; "Dhcpv6DUID"
0x1800156ff  mov     [rsp+60h+cbData], r13d; cbData
0x180015704  xor     r8d, r8d; Reserved
0x180015707  mov     [rsp+60h+lpData], r14; lpData
0x18001570c  call    cs:__imp_RegSetValueExW
0x180015713  nop     dword ptr [rax+rax+00h]
0x180015718  mov     esi, eax
0x18001571a  test    eax, eax
0x18001571c  jnz     short loc_180015789
0x18001571e  test    r12d, r12d
0x180015721  jnz     short loc_180015766
0x180015723  test    byte ptr cs:Microsoft_Windows_DHCPv6_ClientEnableBits, 40h
0x18001572a  jz      short loc_18001575D
0x18001572c  mov     [rsp+60h+var_18], r14
0x180015731  lea     rax, [r14+8]
0x180015735  mov     [rsp+60h+var_20], r13d
0x18001573a  lea     ecx, [r13-8]
0x18001573e  mov     [rsp+60h+var_28], rax
0x180015743  lea     r9, [rbx+8]
0x180015747  mov     [rsp+60h+var_30], ecx
0x18001574b  lea     r8d, [rdi-8]
0x18001574f  mov     qword ptr [rsp+60h+cbData], rbx
0x180015754  mov     dword ptr [rsp+60h+lpData], edi
0x180015758  call    McTemplateU0qbr0qbr2qbr4qbr6_EtwEventWriteTransfer
0x18001575d  lea     rcx, [rbp+arg_18]
0x180015761  call    DhcpFree
0x180015766  mov     edi, r13d
0x180015769  mov     rbx, r14
0x18001576c  movzx   eax, di
0x18001576f  mov     [r15+1D0h], eax
0x180015776  mov     cs:dword_180042510, 1
0x180015780  mov     [r15+1C8h], rbx
0x180015787  jmp     short loc_1800157D0
0x180015789  test    rbx, rbx
0x18001578c  jz      short loc_180015797
0x18001578e  lea     rcx, [rbp+arg_18]
0x180015792  call    DhcpFree
0x180015797  test    r14, r14
0x18001579a  jz      short loc_1800157A5
0x18001579c  lea     rcx, [rbp+var_10]
0x1800157a0  call    DhcpFree
0x1800157a5  test    byte ptr cs:xmmword_1800423E0, 2
0x1800157ac  jz      short loc_1800157D0
0x1800157ae  mov     rax, [r15+18h]
0x1800157b2  lea     r8, WPP_80912ccc52483efd9cc4ca3c8a600041_Traceguids
0x1800157b9  mov     edx, 1Dh
0x1800157be  mov     [rsp+60h+lpData], rax
0x1800157c3  mov     ecx, 401h
0x1800157c8  mov     r9d, esi
0x1800157cb  call    WPP_SF_dJ
0x1800157d0  mov     rbx, [rsp+60h+arg_0]
0x1800157d8  mov     eax, esi
0x1800157da  add     rsp, 60h
0x1800157de  pop     r15
0x1800157e0  pop     r14
0x1800157e2  pop     r13
0x1800157e4  pop     r12
0x1800157e6  pop     rdi
0x1800157e7  pop     rsi
0x1800157e8  pop     rbp
0x1800157e9  retn
```
