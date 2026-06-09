# AmOpenFile

- ea: `0x1400157d8`
- end: `0x140015982`
- name: `AmOpenFile`
- size: `426`
- prototype: `__int64 __usercall@<rax>(PMRX_FCB Fcb@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140015674`

## callees

- `0x1400157d8`
- `0x1400159cc`
- `0x1400159fc`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140015900`
- `ntoskrnl!ZwClose` at `0x140015900`
- `ntoskrnl!ZwCreateFile` at `0x1400158c6`
- `ntoskrnl!ZwCreateFile` at `0x1400158c6`
- `rdbss!RxAcquireExclusiveFcbResourceInMRx` at `0x1400158e5`
- `rdbss!RxAcquireExclusiveFcbResourceInMRx` at `0x1400158e5`
- `rdbss!RxReleaseFcbResourceInMRx` at `0x14001587d`
- `rdbss!RxReleaseFcbResourceInMRx` at `0x14001587d`

## pseudocode

```c
__int64 __fastcall AmOpenFile(PMRX_FCB Fcb, struct _UNICODE_STRING *a2, char a3, void **a4, _BYTE *a5)
{
  NTSTATUS v9; // esi
  unsigned int v10; // ebx
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+60h] [rbp-21h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp-11h] BYREF

  memset(&ObjectAttributes, 0, 44);
  v9 = 0;
  IoStatusBlock = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_1fd2e2a3542c3f6b9236c7d5a3294a22_Traceguids);
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = a2;
  ObjectAttributes.Attributes = a3 != 0 ? 576 : 512;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( Fcb && !*a5 && Fcb->Header.FilterContexts.Flink )
  {
    RxReleaseFcbResourceInMRx(Fcb);
    *a5 = 1;
  }
  v10 = ZwCreateFile(a4, 0x80u, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 7u, 1u, 8u, 0, 0);
  if ( Fcb && Fcb->Header.FilterContexts.Flink )
    v9 = RxAcquireExclusiveFcbResourceInMRx(Fcb);
  if ( (v10 & 0x80000000) != 0 )
    goto LABEL_14;
  if ( v9 < 0 )
  {
    v10 = v9;
    ZwClose(*a4);
LABEL_14:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_1fd2e2a3542c3f6b9236c7d5a3294a22_Traceguids, v10);
    return v10;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_1fd2e2a3542c3f6b9236c7d5a3294a22_Traceguids);
  return v10;
}

```

## disassembly

```asm
0x1400157d8  push    rbp
0x1400157da  push    rbx
0x1400157db  push    rsi
0x1400157dc  push    rdi
0x1400157dd  push    r14
0x1400157df  push    r15
0x1400157e1  lea     rbp, [rsp-27h]
0x1400157e6  sub     rsp, 0A8h
0x1400157ed  xorps   xmm0, xmm0
0x1400157f0  xor     eax, eax
0x1400157f2  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.ObjectName], xmm0
0x1400157f6  mov     r14, r9
0x1400157f9  mov     bl, r8b
0x1400157fc  movups  xmmword ptr [rbp+4Fh+ObjectAttributes+1Ch], xmm0
0x140015800  mov     r15, rdx
0x140015803  mov     rdi, rcx
0x140015806  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.Length], xmm0
0x14001580a  xor     esi, esi
0x14001580c  movups  xmmword ptr [rbp+4Fh+IoStatusBlock], xmm0
0x140015810  mov     rcx, cs:WPP_GLOBAL_Control
0x140015817  lea     rax, WPP_GLOBAL_Control
0x14001581e  cmp     rcx, rax
0x140015821  jz      short loc_14001583D
0x140015823  mov     eax, [rcx+2Ch]
0x140015826  test    al, 8
0x140015828  jz      short loc_14001583D
0x14001582a  mov     rcx, [rcx+18h]
0x14001582e  lea     edx, [rsi+11h]
0x140015831  lea     r8, WPP_1fd2e2a3542c3f6b9236c7d5a3294a22_Traceguids
0x140015838  call    WPP_SF_
0x14001583d  neg     bl
0x14001583f  mov     [rbp+4Fh+ObjectAttributes.Length], 30h ; '0'
0x140015846  xorps   xmm0, xmm0
0x140015849  mov     [rbp+4Fh+ObjectAttributes.RootDirectory], rsi
0x14001584d  sbb     eax, eax
0x14001584f  mov     [rbp+4Fh+ObjectAttributes.ObjectName], r15
0x140015853  and     eax, 40h
0x140015856  add     eax, 200h
0x14001585b  mov     [rbp+4Fh+ObjectAttributes.Attributes], eax
0x14001585e  movdqu  xmmword ptr [rbp+4Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x140015863  test    rdi, rdi
0x140015866  jz      short loc_14001588C
0x140015868  mov     rbx, [rbp+4Fh+arg_20]
0x14001586c  cmp     [rbx], sil
0x14001586f  jnz     short loc_14001588C
0x140015871  mov     rdx, [rdi+38h]
0x140015875  test    rdx, rdx
0x140015878  jz      short loc_14001588C
0x14001587a  mov     rcx, rdi; Fcb
0x14001587d  call    cs:__imp_RxReleaseFcbResourceInMRx
0x140015884  nop     dword ptr [rax+rax+00h]
0x140015889  mov     byte ptr [rbx], 1
0x14001588c  mov     [rsp+0D0h+EaLength], esi; EaLength
0x140015890  lea     r9, [rbp+4Fh+IoStatusBlock]; IoStatusBlock
0x140015894  mov     [rsp+0D0h+EaBuffer], rsi; EaBuffer
0x140015899  lea     r8, [rbp+4Fh+ObjectAttributes]; ObjectAttributes
0x14001589d  mov     [rsp+0D0h+CreateOptions], 8; CreateOptions
0x1400158a5  mov     edx, 80h; DesiredAccess
0x1400158aa  mov     [rsp+0D0h+CreateDisposition], 1; CreateDisposition
0x1400158b2  mov     rcx, r14; FileHandle
0x1400158b5  mov     [rsp+0D0h+ShareAccess], 7; ShareAccess
0x1400158bd  mov     [rsp+0D0h+FileAttributes], edx; FileAttributes
0x1400158c1  mov     [rsp+0D0h+AllocationSize], rsi; AllocationSize
0x1400158c6  call    cs:__imp_ZwCreateFile
0x1400158cd  nop     dword ptr [rax+rax+00h]
0x1400158d2  mov     ebx, eax
0x1400158d4  test    rdi, rdi
0x1400158d7  jz      short loc_1400158F3
0x1400158d9  mov     rdx, [rdi+38h]
0x1400158dd  test    rdx, rdx
0x1400158e0  jz      short loc_1400158F3
0x1400158e2  mov     rcx, rdi; Fcb
0x1400158e5  call    cs:__imp_RxAcquireExclusiveFcbResourceInMRx
0x1400158ec  nop     dword ptr [rax+rax+00h]
0x1400158f1  mov     esi, eax
0x1400158f3  test    ebx, ebx
0x1400158f5  js      short loc_14001590C
0x1400158f7  test    esi, esi
0x1400158f9  jns     short loc_140015951
0x1400158fb  mov     ebx, esi
0x1400158fd  mov     rcx, [r14]; Handle
0x140015900  call    cs:__imp_ZwClose
0x140015907  nop     dword ptr [rax+rax+00h]
0x14001590c  mov     rcx, cs:WPP_GLOBAL_Control
0x140015913  lea     rax, WPP_GLOBAL_Control
0x14001591a  cmp     rcx, rax
0x14001591d  jz      short loc_14001593E
0x14001591f  mov     eax, [rcx+2Ch]
0x140015922  test    al, 2
0x140015924  jz      short loc_14001593E
0x140015926  mov     rcx, [rcx+18h]
0x14001592a  lea     r8, WPP_1fd2e2a3542c3f6b9236c7d5a3294a22_Traceguids
0x140015931  mov     edx, 13h
0x140015936  mov     r9d, ebx
0x140015939  call    WPP_SF_d
0x14001593e  mov     eax, ebx
0x140015940  add     rsp, 0A8h
0x140015947  pop     r15
0x140015949  pop     r14
0x14001594b  pop     rdi
0x14001594c  pop     rsi
0x14001594d  pop     rbx
0x14001594e  pop     rbp
0x14001594f  retn
0x140015951  mov     rcx, cs:WPP_GLOBAL_Control
0x140015958  lea     rax, WPP_GLOBAL_Control
0x14001595f  cmp     rcx, rax
0x140015962  jz      short loc_14001593E
0x140015964  mov     eax, [rcx+2Ch]
0x140015967  test    al, 8
0x140015969  jz      short loc_14001593E
0x14001596b  mov     rcx, [rcx+18h]
0x14001596f  lea     r8, WPP_1fd2e2a3542c3f6b9236c7d5a3294a22_Traceguids
0x140015976  mov     edx, 12h
0x14001597b  call    WPP_SF_
0x140015980  jmp     short loc_14001593E
```
