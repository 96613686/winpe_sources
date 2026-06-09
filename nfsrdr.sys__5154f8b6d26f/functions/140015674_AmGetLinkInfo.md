# AmGetLinkInfo

- ea: `0x140015674`
- end: `0x1400157d0`
- name: `AmGetLinkInfo`
- size: `348`
- prototype: `__int64 __usercall@<rax>(PMRX_FCB Fcb@<rcx>, __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x1400150f0`
- `0x140035384`

## callees

- `0x140015674`
- `0x1400157d8`
- `0x1400159cc`
- `0x1400159fc`
- `0x14003aba0`

## import_xrefs

- `ntoskrnl!ZwQueryInformationFile` at `0x14001571c`
- `ntoskrnl!ZwQueryInformationFile` at `0x140015753`
- `ntoskrnl!ZwQueryInformationFile` at `0x14001571c`
- `ntoskrnl!ZwQueryInformationFile` at `0x140015753`
- `ntoskrnl!ZwClose` at `0x14001577b`
- `ntoskrnl!ZwClose` at `0x14001577b`

## pseudocode

```c
__int64 __fastcall AmGetLinkInfo(PMRX_FCB Fcb, struct _UNICODE_STRING *a2, char a3, __int64 a4, _BYTE *a5)
{
  int v9; // ebx
  HANDLE FileHandle; // [rsp+30h] [rbp-40h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+38h] [rbp-38h] BYREF
  __int128 FileInformation; // [rsp+48h] [rbp-28h] BYREF
  __int64 v14; // [rsp+58h] [rbp-18h]

  IoStatusBlock = 0;
  FileHandle = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_1fd2e2a3542c3f6b9236c7d5a3294a22_Traceguids);
  v9 = AmOpenFile(Fcb, a2, a3, &FileHandle, a5);
  if ( v9 >= 0 )
  {
    v9 = ZwQueryInformationFile(FileHandle, &IoStatusBlock, (PVOID)a4, 0x28u, FileBasicInformation);
    if ( v9 >= 0 )
    {
      v14 = 0;
      FileInformation = 0;
      v9 = ZwQueryInformationFile(FileHandle, &IoStatusBlock, &FileInformation, 0x18u, FileStandardInformation);
      if ( v9 >= 0 )
      {
        v9 = 0;
        *(_OWORD *)(a4 + 40) = FileInformation;
      }
    }
    ZwClose(FileHandle);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_1fd2e2a3542c3f6b9236c7d5a3294a22_Traceguids);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140015674  push    rbp
0x140015676  push    rbx
0x140015677  push    rsi
0x140015678  push    rdi
0x140015679  push    r12
0x14001567b  push    r14
0x14001567d  push    r15
0x14001567f  mov     rbp, rsp
0x140015682  sub     rsp, 70h
0x140015686  mov     rax, cs:__security_cookie
0x14001568d  xor     rax, rsp
0x140015690  mov     [rbp+var_10], rax
0x140015694  mov     r15, [rbp+arg_20]
0x140015698  xorps   xmm0, xmm0
0x14001569b  movups  xmmword ptr [rbp+IoStatusBlock], xmm0
0x14001569f  mov     rdi, r9
0x1400156a2  mov     [rbp+FileHandle], 0
0x1400156aa  mov     r14b, r8b
0x1400156ad  mov     rsi, rdx
0x1400156b0  mov     rbx, rcx
0x1400156b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400156ba  lea     r12, WPP_GLOBAL_Control
0x1400156c1  cmp     rcx, r12
0x1400156c4  jz      short loc_1400156E2
0x1400156c6  mov     eax, [rcx+2Ch]
0x1400156c9  test    al, 8
0x1400156cb  jz      short loc_1400156E2
0x1400156cd  mov     rcx, [rcx+18h]
0x1400156d1  lea     r8, WPP_1fd2e2a3542c3f6b9236c7d5a3294a22_Traceguids
0x1400156d8  mov     edx, 14h
0x1400156dd  call    WPP_SF_
0x1400156e2  lea     r9, [rbp+FileHandle]
0x1400156e6  mov     qword ptr [rsp+70h+FileInformationClass], r15; __int64
0x1400156eb  mov     r8b, r14b
0x1400156ee  mov     rdx, rsi
0x1400156f1  mov     rcx, rbx; Fcb
0x1400156f4  call    AmOpenFile
0x1400156f9  mov     ebx, eax
0x1400156fb  test    eax, eax
0x1400156fd  js      loc_140015787
0x140015703  mov     rcx, [rbp+FileHandle]; FileHandle
0x140015707  lea     rdx, [rbp+IoStatusBlock]; IoStatusBlock
0x14001570b  mov     r9d, 28h ; '('; Length
0x140015711  mov     [rsp+70h+FileInformationClass], 4; FileInformationClass
0x140015719  mov     r8, rdi; FileInformation
0x14001571c  call    cs:__imp_ZwQueryInformationFile
0x140015723  nop     dword ptr [rax+rax+00h]
0x140015728  mov     ebx, eax
0x14001572a  test    eax, eax
0x14001572c  js      short loc_140015777
0x14001572e  mov     rcx, [rbp+FileHandle]; FileHandle
0x140015732  lea     r8, [rbp+FileInformation]; FileInformation
0x140015736  xor     eax, eax
0x140015738  mov     [rsp+70h+FileInformationClass], 5; FileInformationClass
0x140015740  xorps   xmm0, xmm0
0x140015743  mov     [rbp+var_18], rax
0x140015747  lea     rdx, [rbp+IoStatusBlock]; IoStatusBlock
0x14001574b  movups  [rbp+FileInformation], xmm0
0x14001574f  lea     r9d, [rax+18h]; Length
0x140015753  call    cs:__imp_ZwQueryInformationFile
0x14001575a  nop     dword ptr [rax+rax+00h]
0x14001575f  mov     ebx, eax
0x140015761  test    eax, eax
0x140015763  js      short loc_140015777
0x140015765  mov     rax, qword ptr [rbp+FileInformation]
0x140015769  xor     ebx, ebx
0x14001576b  mov     [rdi+28h], rax
0x14001576f  mov     rax, qword ptr [rbp+FileInformation+8]
0x140015773  mov     [rdi+30h], rax
0x140015777  mov     rcx, [rbp+FileHandle]; Handle
0x14001577b  call    cs:__imp_ZwClose
0x140015782  nop     dword ptr [rax+rax+00h]
0x140015787  mov     rcx, cs:WPP_GLOBAL_Control
0x14001578e  cmp     rcx, r12
0x140015791  jz      short loc_1400157B2
0x140015793  mov     eax, [rcx+2Ch]
0x140015796  test    al, 8
0x140015798  jz      short loc_1400157B2
0x14001579a  mov     rcx, [rcx+18h]
0x14001579e  lea     r8, WPP_1fd2e2a3542c3f6b9236c7d5a3294a22_Traceguids
0x1400157a5  mov     edx, 15h
0x1400157aa  mov     r9d, ebx
0x1400157ad  call    WPP_SF_d
0x1400157b2  mov     eax, ebx
0x1400157b4  mov     rcx, [rbp+var_10]
0x1400157b8  xor     rcx, rsp; StackCookie
0x1400157bb  call    __security_check_cookie
0x1400157c0  add     rsp, 70h
0x1400157c4  pop     r15
0x1400157c6  pop     r14
0x1400157c8  pop     r12
0x1400157ca  pop     rdi
0x1400157cb  pop     rsi
0x1400157cc  pop     rbx
0x1400157cd  pop     rbp
0x1400157ce  retn
```
