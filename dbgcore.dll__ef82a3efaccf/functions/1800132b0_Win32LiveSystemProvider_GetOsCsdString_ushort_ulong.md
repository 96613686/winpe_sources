# Win32LiveSystemProvider::GetOsCsdString(ushort *,ulong)

- ea: `0x1800132b0`
- end: `0x180013337`
- name: `?GetOsCsdString@Win32LiveSystemProvider@@UEAAJPEAGK@Z`
- size: `135`
- prototype: `int(Win32LiveSystemProvider *__hidden this, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180024940`

## callees

- `0x180001710`
- `0x1800021f4`
- `0x1800132b0`
- `0x18001bec8`

## import_xrefs

- `ntdll!RtlGetVersion` at `0x1800132f4`
- `ntdll!RtlGetVersion` at `0x1800132f4`

## pseudocode

```c
int __fastcall Win32LiveSystemProvider::GetOsCsdString(Win32LiveSystemProvider *this, unsigned __int16 *a2, int a3)
{
  NTSTATUS Version; // eax
  struct _OSVERSIONINFOW VersionInformation; // [rsp+20h] [rbp-138h] BYREF

  memset_0(&VersionInformation.dwMajorVersion, 0, 0x118u);
  VersionInformation.dwOSVersionInfoSize = 284;
  Version = RtlGetVersion(&VersionInformation);
  if ( Version < 0 )
    return Version | 0x10000000;
  GenStrCopyNW(a2, VersionInformation.szCSDVersion, a3);
  return 0;
}

```

## disassembly

```asm
0x1800132b0  mov     [rsp+arg_0], rbx
0x1800132b5  push    rdi
0x1800132b6  sub     rsp, 150h
0x1800132bd  mov     rax, cs:__security_cookie
0x1800132c4  xor     rax, rsp
0x1800132c7  mov     [rsp+158h+var_18], rax
0x1800132cf  mov     edi, r8d
0x1800132d2  lea     rcx, [rsp+158h+VersionInformation.dwMajorVersion]; void *
0x1800132d7  mov     rbx, rdx
0x1800132da  mov     r8d, 118h; Size
0x1800132e0  xor     edx, edx; Val
0x1800132e2  call    memset_0
0x1800132e7  lea     rcx, [rsp+158h+VersionInformation]; lpVersionInformation
0x1800132ec  mov     [rsp+158h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x1800132f4  call    cs:__imp_RtlGetVersion
0x1800132fa  test    eax, eax
0x1800132fc  jns     short loc_180013304
0x1800132fe  bts     eax, 1Ch
0x180013302  jmp     short loc_180013316
0x180013304  mov     r8d, edi; int
0x180013307  lea     rdx, [rsp+158h+VersionInformation.szCSDVersion]; unsigned __int16 *
0x18001330c  mov     rcx, rbx; unsigned __int16 *
0x18001330f  call    ?GenStrCopyNW@@YAPEAGPEAGPEBGH@Z; GenStrCopyNW(ushort *,ushort const *,int)
0x180013314  xor     eax, eax
0x180013316  mov     rcx, [rsp+158h+var_18]
0x18001331e  xor     rcx, rsp; StackCookie
0x180013321  call    __security_check_cookie
0x180013326  mov     rbx, [rsp+158h+arg_0]
0x18001332e  add     rsp, 150h
0x180013335  pop     rdi
0x180013336  retn
```
