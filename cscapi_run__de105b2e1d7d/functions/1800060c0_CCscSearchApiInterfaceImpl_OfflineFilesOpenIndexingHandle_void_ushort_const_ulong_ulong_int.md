# CCscSearchApiInterfaceImpl::OfflineFilesOpenIndexingHandle(void * *,ushort const *,ulong,ulong,int *)

- ea: `0x1800060c0`
- end: `0x1800061ee`
- name: `?OfflineFilesOpenIndexingHandle@CCscSearchApiInterfaceImpl@@UEAAKPEAPEAXPEBGKKPEAH@Z`
- size: `302`
- prototype: `unsigned int(CCscSearchApiInterfaceImpl *__hidden this, void **, const unsigned __int16 *, unsigned int, unsigned int, int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180002a40`
- `0x180002db0`
- `0x1800060c0`
- `0x180009462`

## import_xrefs

- `ntdll!NtClose` at `0x1800061aa`
- `ntdll!NtClose` at `0x1800061aa`
- `ntdll!RtlInitUnicodeString` at `0x180006123`
- `ntdll!RtlInitUnicodeString` at `0x180006123`
- `ntdll!RtlNtStatusToDosError` at `0x1800061d0`
- `ntdll!RtlNtStatusToDosError` at `0x1800061d0`

## pseudocode

```c
ULONG __fastcall CCscSearchApiInterfaceImpl::OfflineFilesOpenIndexingHandle(
        CCscSearchApiInterfaceImpl *this,
        void **a2,
        const unsigned __int16 *a3,
        int a4,
        ULONG a5,
        int *a6)
{
  HANDLE v8; // rdi
  ULONG v10; // r14d
  __int64 v11; // rdx
  NTSTATUS ItemInformation; // ebx
  int v14; // [rsp+30h] [rbp-88h]
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-78h] BYREF
  _DWORD v16[20]; // [rsp+50h] [rbp-68h] BYREF
  HANDLE Handle; // [rsp+C8h] [rbp+10h] BYREF

  v8 = 0;
  Handle = 0;
  DestinationString = 0;
  memset_0(v16, 0, sizeof(v16));
  if ( (a4 & 0x5FEDFF56) != 0 || (v10 = a5, (a5 & 1) == 0) )
  {
    ItemInformation = -1073741811;
    goto LABEL_14;
  }
  RtlInitUnicodeString(&DestinationString, a3);
  if ( a6 )
  {
    LODWORD(v8) = 1;
    if ( !*a6 )
      LODWORD(v8) = 64;
  }
  ItemInformation = CscDriverOpenItemWithDispositionEx(&Handle, v11, &DestinationString, 1052672, a4, v10, v14, (int)v8);
  if ( ItemInformation >= 0 )
  {
    ItemInformation = CscDriverQueryItemInformation(Handle);
    if ( ItemInformation >= 0 )
    {
      if ( (v16[0] & 0x800000) == 0 )
      {
        v8 = Handle;
        goto LABEL_14;
      }
      ItemInformation = -1073741816;
    }
  }
  v8 = Handle;
  if ( Handle )
  {
    NtClose(Handle);
    v8 = 0;
    Handle = 0;
  }
LABEL_14:
  *a2 = v8;
  return RtlNtStatusToDosError(ItemInformation);
}

```

## disassembly

```asm
0x1800060c0  mov     rax, rsp
0x1800060c3  mov     [rax+8], rbx
0x1800060c7  mov     [rax+18h], rbp
0x1800060cb  push    rsi
0x1800060cc  push    rdi
0x1800060cd  push    r14
0x1800060cf  sub     rsp, 0A0h
0x1800060d6  mov     rbp, r8
0x1800060d9  lea     rcx, [rax-68h]; void *
0x1800060dd  mov     rsi, rdx
0x1800060e0  xorps   xmm0, xmm0
0x1800060e3  xor     edi, edi
0x1800060e5  xor     edx, edx; Val
0x1800060e7  mov     r8d, 50h ; 'P'; Size
0x1800060ed  mov     [rax+10h], rdi
0x1800060f1  movups  xmmword ptr [rax-78h], xmm0
0x1800060f5  mov     ebx, r9d
0x1800060f8  call    memset_0
0x1800060fd  test    ebx, 5FEDFF56h
0x180006103  jnz     loc_1800061C6
0x180006109  mov     r14d, [rsp+0B8h+arg_20]
0x180006111  test    r14b, 1
0x180006115  jz      loc_1800061C6
0x18000611b  mov     rdx, rbp; SourceString
0x18000611e  lea     rcx, [rsp+0B8h+DestinationString]; DestinationString
0x180006123  call    cs:__imp_RtlInitUnicodeString
0x180006129  mov     rax, [rsp+0B8h+arg_28]
0x180006131  test    rax, rax
0x180006134  jz      short loc_180006146
0x180006136  cmp     dword ptr [rax], 0
0x180006139  mov     edi, 1
0x18000613e  mov     ecx, 40h ; '@'
0x180006143  cmovz   edi, ecx
0x180006146  mov     [rsp+0B8h+var_80], edi; int
0x18000614a  lea     r8, [rsp+0B8h+DestinationString]
0x18000614f  mov     [rsp+0B8h+var_90], r14d; ULONG
0x180006154  lea     rcx, [rsp+0B8h+Handle]; FileHandle
0x18000615c  mov     r9d, 101000h
0x180006162  mov     [rsp+0B8h+var_98], ebx; int
0x180006166  call    CscDriverOpenItemWithDispositionEx
0x18000616b  mov     ebx, eax
0x18000616d  test    eax, eax
0x18000616f  js      short loc_18000619A
0x180006171  mov     rcx, [rsp+0B8h+Handle]; FileHandle
0x180006179  lea     r8, [rsp+0B8h+var_68]
0x18000617e  xor     edx, edx
0x180006180  call    CscDriverQueryItemInformation
0x180006185  mov     ebx, eax
0x180006187  test    eax, eax
0x180006189  js      short loc_18000619A
0x18000618b  test    [rsp+0B8h+var_68], 800000h
0x180006193  jz      short loc_1800061BC
0x180006195  mov     ebx, 0C0000008h
0x18000619a  mov     rdi, [rsp+0B8h+Handle]
0x1800061a2  test    rdi, rdi
0x1800061a5  jz      short loc_1800061CB
0x1800061a7  mov     rcx, rdi; Handle
0x1800061aa  call    cs:__imp_NtClose
0x1800061b0  xor     edi, edi
0x1800061b2  mov     [rsp+0B8h+Handle], rdi
0x1800061ba  jmp     short loc_1800061CB
0x1800061bc  mov     rdi, [rsp+0B8h+Handle]
0x1800061c4  jmp     short loc_1800061CB
0x1800061c6  mov     ebx, 0C000000Dh
0x1800061cb  mov     ecx, ebx; Status
0x1800061cd  mov     [rsi], rdi
0x1800061d0  call    cs:__imp_RtlNtStatusToDosError
0x1800061d6  lea     r11, [rsp+0B8h+var_18]
0x1800061de  mov     rbx, [r11+20h]
0x1800061e2  mov     rbp, [r11+30h]
0x1800061e6  mov     rsp, r11
0x1800061e9  pop     r14
0x1800061eb  pop     rdi
0x1800061ec  pop     rsi
0x1800061ed  retn
```
