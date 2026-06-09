# CClfsLogFcbPhysical::GetContainerName(ulong,_UNICODE_STRING &,ulong &)

- ea: `0x140046620`
- end: `0x14004678e`
- name: `?GetContainerName@CClfsLogFcbPhysical@@UEAAJKAEAU_UNICODE_STRING@@AEAK@Z`
- size: `366`
- prototype: `int(CClfsLogFcbPhysical *__hidden this, unsigned int, struct _UNICODE_STRING *, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140015640`

## callees

- `0x140005840`
- `0x140038b18`
- `0x140046620`

## import_xrefs

- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140046684`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140046684`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x140046702`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x140046702`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140046757`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140046757`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400466de`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400466de`

## pseudocode

```c
__int64 __fastcall CClfsLogFcbPhysical::GetContainerName(
        CClfsLogFcbPhysical *this,
        int a2,
        struct _UNICODE_STRING *a3,
        unsigned int *a4)
{
  __int16 v6; // bx
  BOOLEAN v8; // si
  int ContainerName; // ebx
  __int64 v10; // rbx
  unsigned int Length; // ecx
  UNICODE_STRING String2; // [rsp+30h] [rbp-48h] BYREF
  UNICODE_STRING DestinationString; // [rsp+40h] [rbp-38h] BYREF
  struct _UNICODE_STRING v15; // [rsp+50h] [rbp-28h] BYREF

  v6 = a2;
  *(_QWORD *)&v15.Length = 0;
  v15.Buffer = 0;
  *(_QWORD *)&DestinationString.Length = 0;
  DestinationString.Buffer = 0;
  *(_QWORD *)&String2.Length = 0;
  String2.Buffer = 0;
  v8 = 0;
  *a4 = 0;
  if ( a2 == -1 )
  {
    ContainerName = -1073741811;
  }
  else
  {
    v8 = ExAcquireResourceSharedLite((PERESOURCE)((char *)this + 200), 1u);
    v10 = v6 & 0x3FF;
    if ( (unsigned int)v10 < *((_DWORD *)this + 354) )
    {
      ContainerName = CClfsBaseFile::GetContainerName(
                        *((CClfsBaseFile **)this + 89),
                        *((_DWORD *)this + v10 + 356),
                        &v15);
      if ( ContainerName >= 0 )
      {
        RtlInitUnicodeString(&DestinationString, L"\\??\\");
        String2 = v15;
        if ( RtlPrefixUnicodeString(&DestinationString, &String2, 0) )
        {
          String2.Buffer += (unsigned __int64)DestinationString.Length >> 1;
          String2.Length -= DestinationString.Length;
          String2.MaximumLength -= DestinationString.Length;
        }
        Length = String2.Length;
        *a4 = String2.Length;
        if ( Length <= a3->MaximumLength )
          RtlCopyUnicodeString(a3, &String2);
        else
          ContainerName = -2147483643;
      }
    }
    else
    {
      ContainerName = -1073741809;
    }
  }
  if ( v8 )
    ClfsReleaseResourceLite((struct _ERESOURCE *)((char *)this + 200));
  return (unsigned int)ContainerName;
}

```

## disassembly

```asm
0x140046620  mov     r11, rsp
0x140046623  mov     [r11+10h], rbx
0x140046627  mov     [r11+18h], rsi
0x14004662b  mov     [r11+8], rcx
0x14004662f  push    rdi
0x140046630  push    r14
0x140046632  push    r15
0x140046634  sub     rsp, 60h
0x140046638  mov     r14, r9
0x14004663b  mov     r15, r8
0x14004663e  mov     ebx, edx
0x140046640  mov     rdi, rcx
0x140046643  xor     eax, eax
0x140046645  mov     [r11-28h], rax
0x140046649  mov     [r11-20h], rax
0x14004664d  mov     [r11-38h], rax
0x140046651  mov     [r11-30h], rax
0x140046655  mov     [r11-48h], rax
0x140046659  mov     [r11-40h], rax
0x14004665d  xor     sil, sil
0x140046660  mov     [rsp+78h+var_58], sil
0x140046665  mov     [r9], eax
0x140046668  cmp     edx, 0FFFFFFFFh
0x14004666b  jnz     short loc_14004667B
0x14004666d  mov     ebx, 0C000000Dh
0x140046672  mov     [rsp+78h+var_54], ebx
0x140046676  jmp     loc_140046764
0x14004667b  add     rcx, 0C8h; Resource
0x140046682  mov     dl, 1; Wait
0x140046684  call    cs:__imp_ExAcquireResourceSharedLite
0x14004668b  nop     dword ptr [rax+rax+00h]
0x140046690  mov     sil, al
0x140046693  mov     [rsp+78h+var_58], al
0x140046697  and     ebx, 3FFh
0x14004669d  cmp     ebx, [rdi+588h]
0x1400466a3  jb      short loc_1400466AC
0x1400466a5  mov     ebx, 0C000000Fh
0x1400466aa  jmp     short loc_140046672
0x1400466ac  lea     r8, [rsp+78h+var_28]; struct _UNICODE_STRING *
0x1400466b1  mov     edx, [rdi+rbx*4+590h]; unsigned int
0x1400466b8  mov     rcx, [rdi+2C8h]; this
0x1400466bf  call    ?GetContainerName@CClfsBaseFile@@QEAAJKAEAU_UNICODE_STRING@@@Z; CClfsBaseFile::GetContainerName(ulong,_UNICODE_STRING &)
0x1400466c4  mov     ebx, eax
0x1400466c6  mov     [rsp+78h+var_54], eax
0x1400466ca  test    eax, eax
0x1400466cc  js      loc_140046764
0x1400466d2  lea     rdx, asc_14001C860; "\\??\\"
0x1400466d9  lea     rcx, [rsp+78h+DestinationString]; DestinationString
0x1400466de  call    cs:__imp_RtlInitUnicodeString
0x1400466e5  nop     dword ptr [rax+rax+00h]
0x1400466ea  movaps  xmm0, xmmword ptr [rsp+78h+var_28.Length]
0x1400466ef  movdqa  xmmword ptr [rsp+78h+String2.Length], xmm0
0x1400466f5  xor     r8d, r8d; CaseInSensitive
0x1400466f8  lea     rdx, [rsp+78h+String2]; String2
0x1400466fd  lea     rcx, [rsp+78h+DestinationString]; String1
0x140046702  call    cs:__imp_RtlPrefixUnicodeString
0x140046709  nop     dword ptr [rax+rax+00h]
0x14004670e  test    al, al
0x140046710  jz      short loc_140046734
0x140046712  movzx   edx, [rsp+78h+DestinationString.Length]
0x140046717  mov     ecx, edx
0x140046719  shr     rcx, 1
0x14004671c  mov     rax, [rsp+78h+String2.Buffer]
0x140046721  lea     rcx, [rax+rcx*2]
0x140046725  mov     [rsp+78h+String2.Buffer], rcx
0x14004672a  sub     [rsp+78h+String2.Length], dx
0x14004672f  sub     [rsp+78h+String2.MaximumLength], dx
0x140046734  movzx   ecx, [rsp+78h+String2.Length]
0x140046739  mov     [r14], ecx
0x14004673c  movzx   eax, word ptr [r15+2]
0x140046741  cmp     ecx, eax
0x140046743  jbe     short loc_14004674F
0x140046745  mov     ebx, 80000005h
0x14004674a  jmp     loc_140046672
0x14004674f  lea     rdx, [rsp+78h+String2]; SourceString
0x140046754  mov     rcx, r15; DestinationString
0x140046757  call    cs:__imp_RtlCopyUnicodeString
0x14004675e  nop     dword ptr [rax+rax+00h]
0x140046763  nop
0x140046764  test    sil, sil
0x140046767  jz      short loc_140046775
0x140046769  lea     rcx, [rdi+0C8h]
0x140046770  call    ClfsReleaseResourceLite
0x140046775  mov     eax, ebx
0x140046777  lea     r11, [rsp+78h+var_18]
0x14004677c  mov     rbx, [r11+28h]
0x140046780  mov     rsi, [r11+30h]
0x140046784  mov     rsp, r11
0x140046787  pop     r15
0x140046789  pop     r14
0x14004678b  pop     rdi
0x14004678c  retn
0x14007fc72  push    rbp
0x14007fc74  sub     rsp, 20h
0x14007fc78  mov     rbp, rdx
0x14007fc7b  cmp     byte ptr [rbp+20h], 0
0x14007fc7f  jz      short loc_14007FC98
0x14007fc81  mov     rcx, [rbp+80h]
0x14007fc88  add     rcx, 0C8h
0x14007fc8f  call    ClfsReleaseResourceLite
0x14007fc94  mov     byte ptr [rbp+20h], 0
0x14007fc98  add     rsp, 20h
0x14007fc9c  pop     rbp
0x14007fc9d  retn
```
