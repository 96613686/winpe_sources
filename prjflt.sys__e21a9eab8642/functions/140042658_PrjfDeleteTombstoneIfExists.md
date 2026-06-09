# PrjfDeleteTombstoneIfExists

- ea: `0x140042658`
- end: `0x140042a7f`
- name: `PrjfDeleteTombstoneIfExists`
- size: `1063`
- prototype: `__int64 __fastcall(PFLT_INSTANCE Instance, PFILE_OBJECT FileObject, __int64, __int64)`
- caller_count: `3`
- callee_count: `9`
- tags: `reparse_path`

## callers

- `0x140007694`
- `0x140007990`
- `0x140043b24`

## callees

- `0x140006570`
- `0x14000ba20`
- `0x14000d128`
- `0x14000d754`
- `0x14000dab0`
- `0x140021550`
- `0x14003be88`
- `0x140041a3c`
- `0x140042658`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140042a3f`
- `ntoskrnl!ObfDereferenceObject` at `0x140042a3f`
- `FLTMGR!FltSetInformationFile` at `0x140042992`
- `FLTMGR!FltSetInformationFile` at `0x140042992`
- `FLTMGR!FltClose` at `0x140042a2a`
- `FLTMGR!FltClose` at `0x140042a2a`
- `FLTMGR!FltQueryInformationFile` at `0x140042860`
- `FLTMGR!FltQueryInformationFile` at `0x140042860`
- `FLTMGR!FltReleaseContext` at `0x140042a54`
- `FLTMGR!FltReleaseContext` at `0x140042a54`

## pseudocode

```c
__int64 __fastcall PrjfDeleteTombstoneIfExists(PFLT_INSTANCE Instance, PFILE_OBJECT FileObject, __int64 a3, __int64 a4)
{
  PrjfOpenAsReparsePoint(a4, a3, Instance, 65664);
  return 0;
}

```

## disassembly

```asm
0x140042658  push    rbp
0x14004265a  push    rbx
0x14004265b  push    rsi
0x14004265c  push    rdi
0x14004265d  push    r14
0x14004265f  push    r15
0x140042661  lea     rbp, [rsp-2Fh]
0x140042666  sub     rsp, 0B8h
0x14004266d  mov     rax, cs:__security_cookie
0x140042674  xor     rax, rsp
0x140042677  mov     [rbp+57h+var_40], rax
0x14004267b  xor     r15d, r15d
0x14004267e  mov     rdi, rcx
0x140042681  xor     ecx, ecx
0x140042683  mov     [rsp+0E0h+var_88], r15
0x140042688  mov     [rbp+57h+var_48], rcx
0x14004268c  mov     rsi, r9
0x14004268f  mov     rax, r8
0x140042692  mov     [rbp+57h+FileHandle], r15
0x140042696  lea     rcx, [rbp+57h+var_80]
0x14004269a  mov     [rbp+57h+FileObject], r15
0x14004269e  mov     [rsp+0E0h+var_90], rcx
0x1400426a3  mov     r14, rdx
0x1400426a6  mov     [rsp+0E0h+var_98], r15
0x1400426ab  lea     rcx, [rbp+57h+FileObject]
0x1400426af  mov     [rsp+0E0h+var_A0], r15
0x1400426b4  xorps   xmm0, xmm0
0x1400426b7  mov     [rsp+0E0h+var_A8], r15
0x1400426bc  mov     r9d, 10080h
0x1400426c2  mov     [rsp+0E0h+var_B0], rcx
0x1400426c7  mov     r8, rdi
0x1400426ca  lea     rcx, [rbp+57h+FileHandle]
0x1400426ce  mov     [rbp+57h+var_80], r15b
0x1400426d2  mov     [rsp+0E0h+LengthReturned], rcx
0x1400426d7  mov     rdx, rax
0x1400426da  mov     rcx, rsi
0x1400426dd  mov     [rbp+57h+var_7F], r15b
0x1400426e1  movups  [rbp+57h+FileInformation], xmm0
0x1400426e5  mov     [rbp+57h+Context], r15
0x1400426e9  mov     [rbp+57h+var_70], r15d
0x1400426ed  call    PrjfOpenAsReparsePoint
0x1400426f2  mov     ebx, eax
0x1400426f4  cmp     eax, 0C0000034h
0x1400426f9  jz      loc_140042A1E
0x1400426ff  cmp     [rbp+57h+var_80], r15b
0x140042703  jz      loc_140042A1E
0x140042709  test    eax, eax
0x14004270b  jns     short loc_140042785
0x14004270d  mov     dl, byte ptr cs:xmmword_14001A3D0+2
0x140042713  lea     rax, WPP_RECORDER_INITIALIZED
0x14004271a  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140042721  setnz   r8b
0x140042725  and     dl, 8
0x140042728  jnz     short loc_140042733
0x14004272a  test    r8b, r8b
0x14004272d  jz      loc_140042A21
0x140042733  mov     dword ptr [rsp+0E0h+var_90], ebx
0x140042737  lea     rax, aOnecoreBaseFsG_6; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14004273e  mov     dword ptr [rsp+0E0h+var_98], 1D5h
0x140042746  mov     [rsp+0E0h+var_A0], rax
0x14004274b  lea     rax, WPP_3f08b24f959433411191d1ccab0ccd17_Traceguids
0x140042752  mov     [rsp+0E0h+var_A8], rax
0x140042757  mov     word ptr [rsp+0E0h+var_B0], 0Eh
0x14004275e  mov     r9, cs:WPP_GLOBAL_Control
0x140042765  mov     ecx, 213h
0x14004276a  mov     dword ptr [rsp+0E0h+LengthReturned], 13h
0x140042772  mov     byte ptr [rsp+0E0h+FileInformationClass], 2
0x140042777  mov     r9, [r9+40h]
0x14004277b  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x140042780  jmp     loc_140042A21
0x140042785  mov     rdx, [rbp+57h+FileObject]; FileObject
0x140042789  lea     rax, [rbp+57h+Context]
0x14004278d  mov     [rsp+0E0h+var_A8], rax; __int64
0x140042792  xor     r9d, r9d
0x140042795  mov     [rsp+0E0h+var_B0], r15; __int64
0x14004279a  mov     r8b, 1
0x14004279d  mov     [rsp+0E0h+LengthReturned], r15; __int64
0x1400427a2  mov     rcx, rdi; Instance
0x1400427a5  mov     qword ptr [rsp+0E0h+FileInformationClass], r15; __int64
0x1400427aa  call    PrjfGetSetFileContext
0x1400427af  mov     ebx, eax
0x1400427b1  test    eax, eax
0x1400427b3  jns     loc_14004283E
0x1400427b9  mov     dl, byte ptr cs:xmmword_14001A3D0+2
0x1400427bf  lea     rax, WPP_RECORDER_INITIALIZED
0x1400427c6  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400427cd  setnz   r8b
0x1400427d1  and     dl, 8
0x1400427d4  jnz     short loc_1400427DF
0x1400427d6  test    r8b, r8b
0x1400427d9  jz      loc_140042A21
0x1400427df  mov     rax, [rbp+57h+FileObject]
0x1400427e3  mov     ecx, 213h
0x1400427e8  mov     r9, cs:WPP_GLOBAL_Control
0x1400427ef  add     rax, 58h ; 'X'
0x1400427f3  mov     [rsp+0E0h+var_88], rax
0x1400427f8  lea     rax, aOnecoreBaseFsG_6; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x1400427ff  mov     dword ptr [rsp+0E0h+var_90], ebx
0x140042803  mov     dword ptr [rsp+0E0h+var_98], 1E8h
0x14004280b  mov     r9, [r9+40h]
0x14004280f  mov     [rsp+0E0h+var_A0], rax
0x140042814  lea     rax, WPP_3f08b24f959433411191d1ccab0ccd17_Traceguids
0x14004281b  mov     [rsp+0E0h+var_A8], rax
0x140042820  mov     word ptr [rsp+0E0h+var_B0], 0Fh
0x140042827  mov     dword ptr [rsp+0E0h+LengthReturned], 13h
0x14004282f  mov     byte ptr [rsp+0E0h+FileInformationClass], 2
0x140042834  call    WPP_RECORDER_AND_TRACE_SF_sDdZ
0x140042839  jmp     loc_140042A21
0x14004283e  mov     rdx, [rbp+57h+FileObject]; FileObject
0x140042842  lea     rax, [rbp+57h+var_70]
0x140042846  mov     [rsp+0E0h+LengthReturned], rax; LengthReturned
0x14004284b  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x14004284f  mov     r9d, 18h; Length
0x140042855  mov     [rsp+0E0h+FileInformationClass], 5; FileInformationClass
0x14004285d  mov     rcx, rdi; Instance
0x140042860  call    cs:__imp_FltQueryInformationFile
0x140042867  nop     dword ptr [rax+rax+00h]
0x14004286c  mov     ebx, eax
0x14004286e  test    eax, eax
0x140042870  jns     short loc_1400428C8
0x140042872  mov     dl, byte ptr cs:xmmword_14001A3D0+2
0x140042878  lea     rax, WPP_RECORDER_INITIALIZED
0x14004287f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140042886  setnz   r8b
0x14004288a  and     dl, 8
0x14004288d  jnz     short loc_140042898
0x14004288f  test    r8b, r8b
0x140042892  jz      loc_140042A21
0x140042898  mov     dword ptr [rsp+0E0h+var_90], ebx
0x14004289c  lea     rax, aOnecoreBaseFsG_6; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x1400428a3  mov     dword ptr [rsp+0E0h+var_98], 1F6h
0x1400428ab  mov     [rsp+0E0h+var_A0], rax
0x1400428b0  lea     rax, WPP_3f08b24f959433411191d1ccab0ccd17_Traceguids
0x1400428b7  mov     [rsp+0E0h+var_A8], rax
0x1400428bc  mov     word ptr [rsp+0E0h+var_B0], 10h
0x1400428c3  jmp     loc_14004275E
0x1400428c8  mov     r8b, byte ptr [rbp+57h+var_48+5]
0x1400428cc  lea     rax, [rbp+57h+Context]
0x1400428d0  mov     [rsp+0E0h+LengthReturned], rax; __int64
0x1400428d5  xor     r9d, r9d
0x1400428d8  mov     rdx, rsi; SourceString
0x1400428db  mov     qword ptr [rsp+0E0h+FileInformationClass], r14; FileObject
0x1400428e0  mov     rcx, rdi; Instance
0x1400428e3  call    PrjfAddInMemoryTombstone
0x1400428e8  mov     ebx, eax
0x1400428ea  test    eax, eax
0x1400428ec  jns     loc_140042975
0x1400428f2  mov     dl, byte ptr cs:xmmword_14001A3D0+2
0x1400428f8  lea     rax, WPP_RECORDER_INITIALIZED
0x1400428ff  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140042906  setnz   r8b
0x14004290a  and     dl, 8
0x14004290d  jnz     short loc_140042914
0x14004290f  test    r8b, r8b
0x140042912  jz      short loc_140042961
0x140042914  mov     r9, cs:WPP_GLOBAL_Control
0x14004291b  lea     rax, aOnecoreBaseFsG_6; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140042922  mov     dword ptr [rsp+0E0h+var_90], ebx
0x140042926  mov     ecx, 213h
0x14004292b  mov     dword ptr [rsp+0E0h+var_98], 203h
0x140042933  mov     [rsp+0E0h+var_A0], rax
0x140042938  lea     rax, WPP_3f08b24f959433411191d1ccab0ccd17_Traceguids
0x14004293f  mov     r9, [r9+40h]
0x140042943  mov     [rsp+0E0h+var_A8], rax
0x140042948  mov     word ptr [rsp+0E0h+var_B0], 11h
0x14004294f  mov     dword ptr [rsp+0E0h+LengthReturned], 13h
0x140042957  mov     byte ptr [rsp+0E0h+FileInformationClass], 2
0x14004295c  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x140042961  mov     ecx, 3
0x140042966  mov     r8d, ebx
0x140042969  mov     edx, ecx
0x14004296b  call    PrjfTelemetryTombstoneFailureOperation
0x140042970  jmp     loc_140042A21
0x140042975  mov     rdx, [rbp+57h+FileObject]; FileObject
0x140042979  lea     r8, [rbp+57h+var_7F]; FileInformation
0x14004297d  mov     r9d, 1; Length
0x140042983  mov     [rbp+57h+var_7F], 1
0x140042987  mov     rcx, rdi; Instance
0x14004298a  mov     [rsp+0E0h+FileInformationClass], 0Dh; FileInformationClass
0x140042992  call    cs:__imp_FltSetInformationFile
0x140042999  nop     dword ptr [rax+rax+00h]
0x14004299e  mov     ebx, eax
0x1400429a0  test    eax, eax
0x1400429a2  jns     short loc_140042A21
0x1400429a4  mov     dl, byte ptr cs:xmmword_14001A3D0+2
0x1400429aa  lea     rax, WPP_RECORDER_INITIALIZED
0x1400429b1  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400429b8  setnz   r8b
0x1400429bc  and     dl, 8
0x1400429bf  jnz     short loc_1400429C6
0x1400429c1  test    r8b, r8b
0x1400429c4  jz      short loc_140042A21
0x1400429c6  mov     rax, [rbp+57h+FileObject]
0x1400429ca  mov     ecx, 213h
0x1400429cf  mov     r9, cs:WPP_GLOBAL_Control
0x1400429d6  mov     dword ptr [rsp+0E0h+var_88], ebx
0x1400429da  mov     [rsp+0E0h+var_90], rax
0x1400429df  lea     rax, aOnecoreBaseFsG_6; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x1400429e6  mov     dword ptr [rsp+0E0h+var_98], 218h
0x1400429ee  mov     r9, [r9+40h]
0x1400429f2  mov     [rsp+0E0h+var_A0], rax
0x1400429f7  lea     rax, WPP_3f08b24f959433411191d1ccab0ccd17_Traceguids
0x1400429fe  mov     [rsp+0E0h+var_A8], rax
0x140042a03  mov     word ptr [rsp+0E0h+var_B0], 12h
0x140042a0a  mov     dword ptr [rsp+0E0h+LengthReturned], 13h
0x140042a12  mov     byte ptr [rsp+0E0h+FileInformationClass], 2
0x140042a17  call    WPP_RECORDER_AND_TRACE_SF_sDqd
0x140042a1c  jmp     short loc_140042A21
0x140042a1e  mov     ebx, r15d
0x140042a21  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x140042a25  test    rcx, rcx
0x140042a28  jz      short loc_140042A36
0x140042a2a  call    cs:__imp_FltClose
0x140042a31  nop     dword ptr [rax+rax+00h]
0x140042a36  mov     rcx, [rbp+57h+FileObject]; Object
0x140042a3a  test    rcx, rcx
0x140042a3d  jz      short loc_140042A4B
0x140042a3f  call    cs:__imp_ObfDereferenceObject
0x140042a46  nop     dword ptr [rax+rax+00h]
0x140042a4b  mov     rcx, [rbp+57h+Context]; Context
0x140042a4f  test    rcx, rcx
0x140042a52  jz      short loc_140042A60
0x140042a54  call    cs:__imp_FltReleaseContext
0x140042a5b  nop     dword ptr [rax+rax+00h]
0x140042a60  mov     eax, ebx
0x140042a62  mov     rcx, [rbp+57h+var_40]
0x140042a66  xor     rcx, rsp; StackCookie
0x140042a69  call    __security_check_cookie
0x140042a6e  add     rsp, 0B8h
0x140042a75  pop     r15
0x140042a77  pop     r14
0x140042a79  pop     rdi
0x140042a7a  pop     rsi
0x140042a7b  pop     rbx
0x140042a7c  pop     rbp
0x140042a7d  retn
```
