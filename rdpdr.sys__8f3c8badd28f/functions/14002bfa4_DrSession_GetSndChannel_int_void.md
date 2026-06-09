# DrSession::GetSndChannel(int,void * *)

- ea: `0x14002bfa4`
- end: `0x14002c0c8`
- name: `?GetSndChannel@DrSession@@QEAAJHPEAPEAX@Z`
- size: `292`
- prototype: `int(DrSession *__hidden this, int, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1400112e0`

## callees

- `0x14000324c`
- `0x14000327c`
- `0x1400032c0`
- `0x14002bfa4`

## import_xrefs

- `ntoskrnl!IoFileObjectType` at `0x14002bffd`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14002c024`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14002c024`

## pseudocode

```c
__int64 __fastcall DrSession::GetSndChannel(DrSession *this, unsigned int a2, void **a3)
{
  void *v6; // rcx
  NTSTATUS v7; // eax
  unsigned int v8; // ebx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 102, WPP_5c887063686c325024567ba4647d07cf_Traceguids, a2);
  v6 = *(void **)((char *)this + (a2 != 0 ? 0x10 : 0) + 1344);
  if ( v6 )
  {
    v7 = ObOpenObjectByPointer(v6, 0x440u, 0, 0xC0100000, (POBJECT_TYPE)IoFileObjectType, 1, a3);
    v8 = v7;
    if ( v7 < 0 )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        return v8;
      if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          103,
          WPP_5c887063686c325024567ba4647d07cf_Traceguids,
          (unsigned int)v7);
    }
  }
  else
  {
    v8 = -1073741823;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      return v8;
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 104, WPP_5c887063686c325024567ba4647d07cf_Traceguids);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_dd(WPP_GLOBAL_Control->AttachedDevice, 105, WPP_5c887063686c325024567ba4647d07cf_Traceguids, a2, v8);
  return v8;
}

```

## disassembly

```asm
0x14002bfa4  push    rbx
0x14002bfa6  push    rbp
0x14002bfa7  push    rsi
0x14002bfa8  push    rdi
0x14002bfa9  sub     rsp, 48h
0x14002bfad  mov     rsi, r8
0x14002bfb0  mov     edi, edx
0x14002bfb2  mov     rbx, rcx
0x14002bfb5  mov     rcx, cs:WPP_GLOBAL_Control
0x14002bfbc  lea     rbp, WPP_GLOBAL_Control
0x14002bfc3  cmp     rcx, rbp
0x14002bfc6  jz      short loc_14002BFE6
0x14002bfc8  cmp     byte ptr [rcx+29h], 2
0x14002bfcc  jb      short loc_14002BFE6
0x14002bfce  mov     rcx, [rcx+18h]
0x14002bfd2  lea     r8, WPP_5c887063686c325024567ba4647d07cf_Traceguids
0x14002bfd9  mov     edx, 66h ; 'f'
0x14002bfde  mov     r9d, edi
0x14002bfe1  call    WPP_SF_d
0x14002bfe6  mov     eax, edi
0x14002bfe8  neg     eax
0x14002bfea  sbb     rcx, rcx
0x14002bfed  and     ecx, 10h
0x14002bff0  mov     rcx, [rcx+rbx+540h]; Object
0x14002bff8  test    rcx, rcx
0x14002bffb  jz      short loc_14002C062
0x14002bffd  mov     rax, cs:__imp_IoFileObjectType
0x14002c004  mov     r9d, 0C0100000h; DesiredAccess
0x14002c00a  mov     [rsp+68h+Handle], rsi; Handle
0x14002c00f  xor     r8d, r8d; PassedAccessState
0x14002c012  mov     [rsp+68h+AccessMode], 1; AccessMode
0x14002c017  mov     rdx, [rax]
0x14002c01a  mov     [rsp+68h+ObjectType], rdx; ObjectType
0x14002c01f  mov     edx, 440h; HandleAttributes
0x14002c024  call    cs:__imp_ObOpenObjectByPointer
0x14002c02b  nop     dword ptr [rax+rax+00h]
0x14002c030  mov     ebx, eax
0x14002c032  test    eax, eax
0x14002c034  jns     short loc_14002C08E
0x14002c036  mov     rcx, cs:WPP_GLOBAL_Control
0x14002c03d  cmp     rcx, rbp
0x14002c040  jz      short loc_14002C0BC
0x14002c042  cmp     byte ptr [rcx+29h], 2
0x14002c046  jb      short loc_14002C08E
0x14002c048  mov     rcx, [rcx+18h]
0x14002c04c  lea     r8, WPP_5c887063686c325024567ba4647d07cf_Traceguids
0x14002c053  mov     edx, 67h ; 'g'
0x14002c058  mov     r9d, eax
0x14002c05b  call    WPP_SF_d
0x14002c060  jmp     short loc_14002C08E
0x14002c062  mov     rcx, cs:WPP_GLOBAL_Control
0x14002c069  mov     ebx, 0C0000001h
0x14002c06e  cmp     rcx, rbp
0x14002c071  jz      short loc_14002C0BC
0x14002c073  cmp     byte ptr [rcx+29h], 2
0x14002c077  jb      short loc_14002C08E
0x14002c079  mov     rcx, [rcx+18h]
0x14002c07d  lea     r8, WPP_5c887063686c325024567ba4647d07cf_Traceguids
0x14002c084  mov     edx, 68h ; 'h'
0x14002c089  call    WPP_SF_
0x14002c08e  mov     rcx, cs:WPP_GLOBAL_Control
0x14002c095  cmp     rcx, rbp
0x14002c098  jz      short loc_14002C0BC
0x14002c09a  cmp     byte ptr [rcx+29h], 4
0x14002c09e  jb      short loc_14002C0BC
0x14002c0a0  mov     rcx, [rcx+18h]
0x14002c0a4  lea     r8, WPP_5c887063686c325024567ba4647d07cf_Traceguids
0x14002c0ab  mov     edx, 69h ; 'i'
0x14002c0b0  mov     dword ptr [rsp+68h+ObjectType], ebx
0x14002c0b4  mov     r9d, edi
0x14002c0b7  call    WPP_SF_dd
0x14002c0bc  mov     eax, ebx
0x14002c0be  add     rsp, 48h
0x14002c0c2  pop     rdi
0x14002c0c3  pop     rsi
0x14002c0c4  pop     rbp
0x14002c0c5  pop     rbx
0x14002c0c6  retn
```
