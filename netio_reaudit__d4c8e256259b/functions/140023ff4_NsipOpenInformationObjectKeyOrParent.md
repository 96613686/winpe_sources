# NsipOpenInformationObjectKeyOrParent

- ea: `0x140023ff4`
- end: `0x14002421a`
- name: `NsipOpenInformationObjectKeyOrParent`
- size: `550`
- prototype: `__int64 __usercall@<rax>(PHANDLE KeyHandle@<rcx>, __int64)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x140023c30`
- `0x14005f2f0`

## callees

- `0x140023ff4`
- `0x140027de0`
- `0x140027e70`
- `0x140050ea4`
- `0x14005fe0c`
- `0x14005fe98`
- `0x140077fa0`
- `0x140078400`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x140024119`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140024119`
- `ntoskrnl!RtlStringFromGUID` at `0x140024061`
- `ntoskrnl!RtlStringFromGUID` at `0x140024061`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x1400240a2`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x1400240a2`

## string_xrefs

- `0x140024084`: `\Registry\Machine\System\CurrentControlSet\Control\Nsi`

## pseudocode

```c
__int64 __fastcall NsipOpenInformationObjectKeyOrParent(
        PHANDLE KeyHandle,
        __int64 a2,
        int a3,
        ACCESS_MASK a4,
        _DWORD *a5)
{
  NTSTATUS PersistedStateLocation; // ebx
  WCHAR *v10; // r14
  __int64 v12; // [rsp+20h] [rbp-E0h]
  unsigned int v13; // [rsp+40h] [rbp-C0h] BYREF
  struct _UNICODE_STRING GuidString; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR v16[256]; // [rsp+60h] [rbp-A0h] BYREF

  GuidString = 0;
  memset(v16, 0, sizeof(v16));
  v13 = 0;
  PersistedStateLocation = RtlStringFromGUID((const GUID *const)(a2 + 8), &GuidString);
  if ( PersistedStateLocation < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        23,
        WPP_d5c76eba730233b98a5ea3d25d1e0dd0_Traceguids,
        (unsigned int)PersistedStateLocation);
    }
  }
  else
  {
    PersistedStateLocation = RtlGetPersistedStateLocation(
                               L"NsiPersistentStore",
                               0,
                               L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\Nsi",
                               0,
                               v16,
                               512,
                               &v13);
    if ( PersistedStateLocation < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          24,
          WPP_d5c76eba730233b98a5ea3d25d1e0dd0_Traceguids,
          (unsigned int)PersistedStateLocation);
      }
    }
    else
    {
      LODWORD(v12) = a3;
      v10 = &v16[((unsigned __int64)v13 >> 1) - 1];
      if ( StringCbPrintfW(v10, 512LL - v13, L"\\%ls\\%u", GuidString.Buffer, v12) < 0 )
      {
        PersistedStateLocation = -1073741789;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
        {
          WPP_SF_SDD(WPP_GLOBAL_Control->AttachedDevice, 25, (_DWORD)WPP_GLOBAL_Control, GuidString.Buffer, a3);
        }
      }
      else
      {
        PersistedStateLocation = NsipOpenKey(KeyHandle, v16, a4);
        if ( PersistedStateLocation == -1073741772 )
        {
          if ( StringCbPrintfW(v10, 512LL - v13, L"\\%ls", GuidString.Buffer) >= 0 )
          {
            *v10 = 0;
            PersistedStateLocation = NsipOpenKey(KeyHandle, v16, a4);
            if ( a5 )
              *a5 = 0;
          }
          else
          {
            PersistedStateLocation = -1073741789;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
            {
              WPP_SF_SD(WPP_GLOBAL_Control->AttachedDevice, 26, (_DWORD)WPP_GLOBAL_Control, GuidString.Buffer, 35);
            }
          }
        }
        else if ( a5 )
        {
          *a5 = 2;
        }
      }
    }
    RtlFreeUnicodeString(&GuidString);
  }
  return (unsigned int)PersistedStateLocation;
}

```

## disassembly

```asm
0x140023ff4  push    rbp
0x140023ff6  push    rbx
0x140023ff7  push    rsi
0x140023ff8  push    rdi
0x140023ff9  push    r12
0x140023ffb  push    r13
0x140023ffd  push    r14
0x140023fff  push    r15
0x140024001  lea     rbp, [rsp-178h]
0x140024009  sub     rsp, 278h
0x140024010  mov     rax, cs:__security_cookie
0x140024017  xor     rax, rsp
0x14002401a  mov     [rbp+1B0h+var_50], rax
0x140024021  mov     rdi, [rbp+1B0h+arg_20]
0x140024028  mov     r15d, r8d
0x14002402b  mov     rbx, rdx
0x14002402e  mov     r12, rcx
0x140024031  xorps   xmm0, xmm0
0x140024034  lea     rcx, [rsp+2B0h+var_250]; void *
0x140024039  mov     esi, 200h
0x14002403e  xor     edx, edx; Val
0x140024040  mov     r8d, esi; Size
0x140024043  mov     r13d, r9d
0x140024046  movups  xmmword ptr [rsp+2B0h+GuidString.Length], xmm0
0x14002404b  call    memset
0x140024050  lea     rcx, [rbx+8]; Guid
0x140024054  mov     [rsp+2B0h+var_270], 0
0x14002405c  lea     rdx, [rsp+2B0h+GuidString]; GuidString
0x140024061  call    cs:__imp_RtlStringFromGUID
0x140024068  nop     dword ptr [rax+rax+00h]
0x14002406d  mov     ebx, eax
0x14002406f  test    eax, eax
0x140024071  js      loc_140024187
0x140024077  lea     rax, [rsp+2B0h+var_270]
0x14002407c  xor     r9d, r9d
0x14002407f  mov     [rsp+2B0h+var_280], rax
0x140024084  lea     r8, NsiDefaultPersistentStoreRootKey
0x14002408b  lea     rax, [rsp+2B0h+var_250]
0x140024090  mov     [rsp+2B0h+var_288], esi
0x140024094  xor     edx, edx
0x140024096  mov     [rsp+2B0h+var_290], rax
0x14002409b  lea     rcx, aNsipersistents
0x1400240a2  call    cs:__imp_RtlGetPersistedStateLocation
0x1400240a9  nop     dword ptr [rax+rax+00h]
0x1400240ae  mov     ebx, eax
0x1400240b0  test    eax, eax
0x1400240b2  js      loc_14002414B
0x1400240b8  mov     ecx, [rsp+2B0h+var_270]
0x1400240bc  lea     r8, aLsU
0x1400240c3  mov     r9, [rsp+2B0h+GuidString.Buffer]
0x1400240c8  mov     eax, ecx
0x1400240ca  shr     rax, 1
0x1400240cd  mov     edx, esi
0x1400240cf  sub     rdx, rcx; cbDest
0x1400240d2  mov     dword ptr [rsp+2B0h+var_290], r15d
0x1400240d7  lea     r14, [rsp+rax*2+2B0h+pszDest]
0x1400240dc  mov     rcx, r14; pszDest
0x1400240df  call    StringCbPrintfW
0x1400240e4  test    eax, eax
0x1400240e6  js      loc_1400241CA
0x1400240ec  mov     r8d, r13d
0x1400240ef  lea     rdx, [rsp+2B0h+var_250]
0x1400240f4  mov     rcx, r12; KeyHandle
0x1400240f7  call    NsipOpenKey
0x1400240fc  mov     ebx, eax
0x1400240fe  cmp     eax, 0C0000034h
0x140024103  jz      loc_14007B3EE
0x140024109  test    rdi, rdi
0x14002410c  jz      short loc_140024114
0x14002410e  mov     dword ptr [rdi], 2
0x140024114  lea     rcx, [rsp+2B0h+GuidString]; UnicodeString
0x140024119  call    cs:__imp_RtlFreeUnicodeString
0x140024120  nop     dword ptr [rax+rax+00h]
0x140024125  mov     eax, ebx
0x140024127  mov     rcx, [rbp+1B0h+var_50]
0x14002412e  xor     rcx, rsp; StackCookie
0x140024131  call    __security_check_cookie
0x140024136  add     rsp, 278h
0x14002413d  pop     r15
0x14002413f  pop     r14
0x140024141  pop     r13
0x140024143  pop     r12
0x140024145  pop     rdi
0x140024146  pop     rsi
0x140024147  pop     rbx
0x140024148  pop     rbp
0x140024149  retn
0x14002414b  mov     r10, cs:WPP_GLOBAL_Control
0x140024152  lea     rcx, WPP_GLOBAL_Control
0x140024159  cmp     r10, rcx
0x14002415c  jz      short loc_140024114
0x14002415e  cmp     byte ptr [r10+29h], 2
0x140024163  jb      short loc_140024114
0x140024165  mov     eax, [r10+2Ch]
0x140024169  test    al, 10h
0x14002416b  jz      short loc_140024114
0x14002416d  mov     rcx, [r10+18h]
0x140024171  lea     r8, WPP_d5c76eba730233b98a5ea3d25d1e0dd0_Traceguids
0x140024178  mov     edx, 18h
0x14002417d  mov     r9d, ebx
0x140024180  call    WPP_SF_d
0x140024185  jmp     short loc_140024114
0x140024187  mov     r10, cs:WPP_GLOBAL_Control
0x14002418e  lea     rcx, WPP_GLOBAL_Control
0x140024195  cmp     r10, rcx
0x140024198  jz      short loc_140024125
0x14002419a  cmp     byte ptr [r10+29h], 2
0x14002419f  jb      short loc_140024125
0x1400241a1  mov     eax, [r10+2Ch]
0x1400241a5  test    al, 10h
0x1400241a7  jz      loc_140024125
0x1400241ad  mov     rcx, [r10+18h]
0x1400241b1  lea     r8, WPP_d5c76eba730233b98a5ea3d25d1e0dd0_Traceguids
0x1400241b8  mov     edx, 17h
0x1400241bd  mov     r9d, ebx
0x1400241c0  call    WPP_SF_d
0x1400241c5  jmp     loc_140024125
0x1400241ca  mov     ebx, 0C0000023h
0x1400241cf  mov     r8, cs:WPP_GLOBAL_Control
0x1400241d6  lea     rcx, WPP_GLOBAL_Control
0x1400241dd  cmp     r8, rcx
0x1400241e0  jz      loc_140024114
0x1400241e6  cmp     byte ptr [r8+29h], 2
0x1400241eb  jb      loc_140024114
0x1400241f1  mov     eax, [r8+2Ch]
0x1400241f5  test    al, 10h
0x1400241f7  jz      loc_140024114
0x1400241fd  mov     r9, [rsp+2B0h+GuidString.Buffer]
0x140024202  mov     edx, 19h
0x140024207  mov     rcx, [r8+18h]
0x14002420b  mov     dword ptr [rsp+2B0h+var_290], r15d
0x140024210  call    WPP_SF_SDD
0x140024215  jmp     loc_140024114
0x14007b3ee  mov     eax, [rsp+2B0h+var_270]
0x14007b3f2  lea     r8, aLs
0x14007b3f9  mov     r9, [rsp+2B0h+GuidString.Buffer]
0x14007b3fe  sub     rsi, rax
0x14007b401  mov     rdx, rsi; cbDest
0x14007b404  mov     rcx, r14; pszDest
0x14007b407  call    StringCbPrintfW
0x14007b40c  test    eax, eax
0x14007b40e  jns     short loc_14007B464
0x14007b410  mov     ebx, 0C0000023h
0x14007b415  mov     r8, cs:WPP_GLOBAL_Control
0x14007b41c  lea     rcx, WPP_GLOBAL_Control
0x14007b423  cmp     r8, rcx
0x14007b426  jz      loc_140024114
0x14007b42c  cmp     byte ptr [r8+29h], 2
0x14007b431  jb      loc_140024114
0x14007b437  mov     eax, [r8+2Ch]
0x14007b43b  test    al, 10h
0x14007b43d  jz      loc_140024114
0x14007b443  mov     r9, [rsp+2B0h+GuidString.Buffer]
0x14007b448  mov     edx, 1Ah
0x14007b44d  mov     rcx, [r8+18h]
0x14007b451  mov     dword ptr [rsp+2B0h+var_290], 0C0000023h
0x14007b459  call    WPP_SF_SD
0x14007b45e  nop
0x14007b45f  jmp     loc_140024114
0x14007b464  xor     eax, eax
0x14007b466  lea     rdx, [rsp+2B0h+var_250]
0x14007b46b  mov     r8d, r13d
0x14007b46e  mov     [r14], ax
0x14007b472  mov     rcx, r12; KeyHandle
0x14007b475  call    NsipOpenKey
0x14007b47a  mov     ebx, eax
0x14007b47c  test    rdi, rdi
0x14007b47f  jz      loc_140024114
0x14007b485  mov     dword ptr [rdi], 0
0x14007b48b  jmp     loc_140024114
```
