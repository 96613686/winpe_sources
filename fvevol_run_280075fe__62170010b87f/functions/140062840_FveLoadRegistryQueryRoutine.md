# FveLoadRegistryQueryRoutine

- ea: `0x140062840`
- end: `0x14006296f`
- name: `FveLoadRegistryQueryRoutine`
- size: `303`
- prototype: `__int64 __usercall@<rax>(PCWSTR SourceString@<rcx>, int, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140008dc0`
- `0x140021a00`
- `0x140062840`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x14006290b`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14006290b`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400628bb`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400628f2`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400628bb`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400628f2`

## pseudocode

```c
__int64 __fastcall FveLoadRegistryQueryRoutine(
        PCWSTR SourceString,
        int a2,
        const void *a3,
        unsigned int a4,
        int a5,
        __int64 a6)
{
  size_t v6; // rbp
  const WCHAR *v10; // rdx
  unsigned int i; // esi
  __int64 v12; // rbx
  const WCHAR *v13; // rdx
  UNICODE_STRING String2; // [rsp+20h] [rbp-58h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-48h] BYREF

  v6 = a4;
  DestinationString = 0;
  String2 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 50, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids);
  }
  v10 = (const WCHAR *)&qword_140033D40;
  if ( SourceString )
    v10 = SourceString;
  RtlInitUnicodeString(&DestinationString, v10);
  for ( i = 0; ; ++i )
  {
    v12 = 56LL * i;
    v13 = *(const WCHAR **)(v12 + a6 + 24);
    if ( !v13 )
      break;
    if ( a2 == *(_DWORD *)(v12 + a6 + 32)
      && (_DWORD)v6 == *(_DWORD *)(v12 + a6 + 48)
      && a3 != *(const void **)(v12 + a6 + 40) )
    {
      RtlInitUnicodeString(&String2, v13);
      if ( !RtlCompareUnicodeString(&DestinationString, &String2, 1u) )
      {
        memmove(*(void **)(v12 + a6 + 40), a3, v6);
        break;
      }
    }
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 51, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids);
  }
  return 0;
}

```

## disassembly

```asm
0x140062840  push    rbx
0x140062842  push    rbp
0x140062843  push    rsi
0x140062844  push    rdi
0x140062845  push    r12
0x140062847  push    r14
0x140062849  push    r15
0x14006284b  sub     rsp, 40h
0x14006284f  mov     rdi, [rsp+78h+arg_28]
0x140062857  xorps   xmm0, xmm0
0x14006285a  xorps   xmm1, xmm1
0x14006285d  mov     ebp, r9d
0x140062860  movups  xmmword ptr [rsp+78h+DestinationString.Length], xmm0
0x140062865  mov     r14, r8
0x140062868  mov     r15d, edx
0x14006286b  movups  xmmword ptr [rsp+78h+String2.Length], xmm1
0x140062870  mov     rbx, rcx
0x140062873  mov     rcx, cs:WPP_GLOBAL_Control
0x14006287a  lea     r12, WPP_GLOBAL_Control
0x140062881  cmp     rcx, r12
0x140062884  jz      short loc_1400628A8
0x140062886  mov     eax, [rcx+2Ch]
0x140062889  test    al, 8
0x14006288b  jz      short loc_1400628A8
0x14006288d  cmp     byte ptr [rcx+29h], 5
0x140062891  jb      short loc_1400628A8
0x140062893  mov     rcx, [rcx+18h]
0x140062897  lea     r8, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids
0x14006289e  mov     edx, 32h ; '2'
0x1400628a3  call    WPP_SF_
0x1400628a8  test    rbx, rbx
0x1400628ab  lea     rdx, qword_140033D40
0x1400628b2  lea     rcx, [rsp+78h+DestinationString]; DestinationString
0x1400628b7  cmovnz  rdx, rbx; SourceString
0x1400628bb  call    cs:__imp_RtlInitUnicodeString
0x1400628c2  nop     dword ptr [rax+rax+00h]
0x1400628c7  xor     esi, esi
0x1400628c9  mov     eax, esi
0x1400628cb  imul    rbx, rax, 38h ; '8'
0x1400628cf  mov     rdx, [rbx+rdi+18h]; SourceString
0x1400628d4  test    rdx, rdx
0x1400628d7  jz      short loc_14006292F
0x1400628d9  cmp     r15d, [rbx+rdi+20h]
0x1400628de  jnz     short loc_14006291B
0x1400628e0  cmp     ebp, [rbx+rdi+30h]
0x1400628e4  jnz     short loc_14006291B
0x1400628e6  cmp     r14, [rbx+rdi+28h]
0x1400628eb  jz      short loc_14006291B
0x1400628ed  lea     rcx, [rsp+78h+String2]; DestinationString
0x1400628f2  call    cs:__imp_RtlInitUnicodeString
0x1400628f9  nop     dword ptr [rax+rax+00h]
0x1400628fe  mov     r8b, 1; CaseInSensitive
0x140062901  lea     rdx, [rsp+78h+String2]; String2
0x140062906  lea     rcx, [rsp+78h+DestinationString]; String1
0x14006290b  call    cs:__imp_RtlCompareUnicodeString
0x140062912  nop     dword ptr [rax+rax+00h]
0x140062917  test    eax, eax
0x140062919  jz      short loc_14006291F
0x14006291b  inc     esi
0x14006291d  jmp     short loc_1400628C9
0x14006291f  mov     rcx, [rbx+rdi+28h]; void *
0x140062924  mov     r8, rbp; Size
0x140062927  mov     rdx, r14; Src
0x14006292a  call    memmove
0x14006292f  mov     rcx, cs:WPP_GLOBAL_Control
0x140062936  cmp     rcx, r12
0x140062939  jz      short loc_14006295D
0x14006293b  mov     eax, [rcx+2Ch]
0x14006293e  test    al, 8
0x140062940  jz      short loc_14006295D
0x140062942  cmp     byte ptr [rcx+29h], 5
0x140062946  jb      short loc_14006295D
0x140062948  mov     rcx, [rcx+18h]
0x14006294c  lea     r8, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids
0x140062953  mov     edx, 33h ; '3'
0x140062958  call    WPP_SF_
0x14006295d  xor     eax, eax
0x14006295f  add     rsp, 40h
0x140062963  pop     r15
0x140062965  pop     r14
0x140062967  pop     r12
0x140062969  pop     rdi
0x14006296a  pop     rsi
0x14006296b  pop     rbp
0x14006296c  pop     rbx
0x14006296d  retn
```
