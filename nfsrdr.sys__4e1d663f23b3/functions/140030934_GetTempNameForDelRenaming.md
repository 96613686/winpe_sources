# GetTempNameForDelRenaming

- ea: `0x140030934`
- end: `0x140030b00`
- name: `GetTempNameForDelRenaming`
- size: `460`
- prototype: `__int64 __fastcall(__int64, __int64, struct _UNICODE_STRING *, const UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140030ef0`

## callees

- `0x140003510`
- `0x140005c90`
- `0x1400159cc`
- `0x140030934`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400309ee`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400309ee`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140030a0e`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140030a0e`
- `ntoskrnl!RtlIntegerToUnicodeString` at `0x140030a6d`
- `ntoskrnl!RtlIntegerToUnicodeString` at `0x140030a6d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140030ad9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140030ad9`
- `ntoskrnl!ExAllocatePool2` at `0x14003098a`
- `ntoskrnl!ExAllocatePool2` at `0x14003098a`

## pseudocode

```c
__int64 __fastcall GetTempNameForDelRenaming(
        __int64 a1,
        __int64 a2,
        struct _UNICODE_STRING *a3,
        const UNICODE_STRING *a4)
{
  __int64 v4; // r12
  __int64 MaximumLength; // rdx
  WCHAR *Pool2; // rbp
  NTSTATUS appended; // ebx
  USHORT Length; // r15
  unsigned __int64 v13; // rcx
  int v14; // esi
  struct _UNICODE_STRING String; // [rsp+30h] [rbp-48h] BYREF
  __int64 v17; // [rsp+88h] [rbp+10h] BYREF

  v4 = *(_QWORD *)(a2 + 80);
  a3->Buffer = 0;
  MaximumLength = a4[4].MaximumLength;
  v17 = 0;
  String = 0;
  Pool2 = (WCHAR *)ExAllocatePool2(258, MaximumLength + 1024, 827483726);
  if ( Pool2 )
  {
    a3->MaximumLength = a4[4].MaximumLength + 1024;
    a3->Length = 0;
    a3->Buffer = Pool2;
    appended = RtlAppendUnicodeStringToString(a3, a4 + 4);
    if ( appended >= 0 )
    {
      appended = RtlAppendUnicodeToString(a3, L"\\.nfs");
      if ( appended >= 0 )
      {
        Length = a3->Length;
        v13 = a3->Length;
        String.MaximumLength = a3->MaximumLength - a3->Length;
        String.Length = 0;
        v14 = 0;
        String.Buffer = &a3->Buffer[v13 >> 1];
        while ( v14 < 0x7FFF )
        {
          appended = RtlIntegerToUnicodeString(MEMORY[0xFFFFF78000000014], 0, &String);
          if ( appended < 0 )
            goto LABEL_15;
          a3->Length = Length + String.Length;
          if ( (int)CaseInsensitiveLookup(a1, a2, &a3->Length, (__int64)a4, 1, &v17) < 0 )
            return 0;
          HacDereference(v4, v17);
          ++v14;
        }
        appended = -1073741697;
      }
    }
LABEL_15:
    ExFreePoolWithTag(Pool2, 0);
    return (unsigned int)appended;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 120, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
    return 3221225626LL;
  }
}

```

## disassembly

```asm
0x140030934  mov     rax, rsp
0x140030937  mov     [rax+18h], rbx
0x14003093b  mov     [rax+8], rcx
0x14003093f  push    rbp
0x140030940  push    rsi
0x140030941  push    rdi
0x140030942  push    r12
0x140030944  push    r13
0x140030946  push    r14
0x140030948  push    r15
0x14003094a  sub     rsp, 40h
0x14003094e  mov     r12, [rdx+50h]
0x140030952  mov     r13, rdx
0x140030955  mov     qword ptr [r8+8], 0
0x14003095d  mov     rdi, r8
0x140030960  movzx   edx, word ptr [r9+42h]
0x140030965  xorps   xmm0, xmm0
0x140030968  mov     ebx, 400h
0x14003096d  mov     qword ptr [rax+10h], 0
0x140030975  add     rdx, rbx
0x140030978  mov     ecx, 102h
0x14003097d  mov     r8d, 3152664Eh
0x140030983  mov     r14, r9
0x140030986  movups  xmmword ptr [rax-48h], xmm0
0x14003098a  call    cs:__imp_ExAllocatePool2
0x140030991  nop     dword ptr [rax+rax+00h]
0x140030996  mov     rbp, rax
0x140030999  test    rax, rax
0x14003099c  jnz     short loc_1400309D5
0x14003099e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400309a5  lea     rax, WPP_GLOBAL_Control
0x1400309ac  cmp     rcx, rax
0x1400309af  jz      short loc_1400309CB
0x1400309b1  mov     eax, [rcx+2Ch]
0x1400309b4  test    al, 1
0x1400309b6  jz      short loc_1400309CB
0x1400309b8  mov     rcx, [rcx+18h]
0x1400309bc  lea     edx, [rbp+78h]
0x1400309bf  lea     r8, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids
0x1400309c6  call    WPP_SF_
0x1400309cb  mov     eax, 0C000009Ah
0x1400309d0  jmp     loc_140030AE7
0x1400309d5  add     bx, [r14+42h]
0x1400309da  lea     rdx, [r14+40h]; Source
0x1400309de  xor     eax, eax
0x1400309e0  mov     [rdi+2], bx
0x1400309e4  mov     rcx, rdi; Destination
0x1400309e7  mov     [rdi], ax
0x1400309ea  mov     [rdi+8], rbp
0x1400309ee  call    cs:__imp_RtlAppendUnicodeStringToString
0x1400309f5  nop     dword ptr [rax+rax+00h]
0x1400309fa  mov     ebx, eax
0x1400309fc  test    eax, eax
0x1400309fe  js      loc_140030AD4
0x140030a04  lea     rdx, aNfs; "\\.nfs"
0x140030a0b  mov     rcx, rdi; Destination
0x140030a0e  call    cs:__imp_RtlAppendUnicodeToString
0x140030a15  nop     dword ptr [rax+rax+00h]
0x140030a1a  mov     ebx, eax
0x140030a1c  test    eax, eax
0x140030a1e  js      loc_140030AD4
0x140030a24  movzx   eax, word ptr [rdi+2]
0x140030a28  movzx   r15d, word ptr [rdi]
0x140030a2c  sub     ax, r15w
0x140030a30  mov     ecx, r15d
0x140030a33  mov     [rsp+78h+String.MaximumLength], ax
0x140030a38  xor     eax, eax
0x140030a3a  shr     rcx, 1
0x140030a3d  mov     [rsp+78h+String.Length], ax
0x140030a42  xor     esi, esi
0x140030a44  mov     rax, [rdi+8]
0x140030a48  lea     rcx, [rax+rcx*2]
0x140030a4c  mov     [rsp+78h+String.Buffer], rcx
0x140030a51  cmp     esi, 7FFFh
0x140030a57  jge     short loc_140030ACF
0x140030a59  mov     rcx, 0FFFFF78000000014h
0x140030a63  lea     r8, [rsp+78h+String]; String
0x140030a68  xor     edx, edx; Base
0x140030a6a  mov     rcx, [rcx]; Value
0x140030a6d  call    cs:__imp_RtlIntegerToUnicodeString
0x140030a74  nop     dword ptr [rax+rax+00h]
0x140030a79  mov     ebx, eax
0x140030a7b  test    eax, eax
0x140030a7d  js      short loc_140030AD4
0x140030a7f  movzx   eax, [rsp+78h+String.Length]
0x140030a84  mov     r9, r14
0x140030a87  mov     rcx, [rsp+78h+arg_0]
0x140030a8f  add     ax, r15w
0x140030a93  mov     [rdi], ax
0x140030a96  mov     r8, rdi
0x140030a99  lea     rax, [rsp+78h+arg_8]
0x140030aa1  mov     rdx, r13
0x140030aa4  mov     [rsp+78h+var_50], rax
0x140030aa9  mov     [rsp+78h+var_58], 1
0x140030aae  call    CaseInsensitiveLookup
0x140030ab3  test    eax, eax
0x140030ab5  js      short loc_140030ACB
0x140030ab7  mov     rdx, [rsp+78h+arg_8]
0x140030abf  mov     rcx, r12
0x140030ac2  call    HacDereference
0x140030ac7  inc     esi
0x140030ac9  jmp     short loc_140030A51
0x140030acb  xor     eax, eax
0x140030acd  jmp     short loc_140030AE7
0x140030acf  mov     ebx, 0C000007Fh
0x140030ad4  xor     edx, edx; Tag
0x140030ad6  mov     rcx, rbp; P
0x140030ad9  call    cs:__imp_ExFreePoolWithTag
0x140030ae0  nop     dword ptr [rax+rax+00h]
0x140030ae5  mov     eax, ebx
0x140030ae7  mov     rbx, [rsp+78h+arg_10]
0x140030aef  add     rsp, 40h
0x140030af3  pop     r15
0x140030af5  pop     r14
0x140030af7  pop     r13
0x140030af9  pop     r12
0x140030afb  pop     rdi
0x140030afc  pop     rsi
0x140030afd  pop     rbp
0x140030afe  retn
```
