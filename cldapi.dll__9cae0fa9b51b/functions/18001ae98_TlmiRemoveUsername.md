# TlmiRemoveUsername

- ea: `0x18001ae98`
- end: `0x18001af73`
- name: `TlmiRemoveUsername`
- size: `219`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180018564`
- `0x180019ed8`
- `0x18001af80`

## callees

- `0x18001ae98`

## import_xrefs

- `ntdll!RtlEqualUnicodeString` at `0x18001aee8`
- `ntdll!RtlEqualUnicodeString` at `0x18001aee8`

## pseudocode

```c
unsigned __int64 __fastcall TlmiRemoveUsername(WCHAR *a1, USHORT a2)
{
  unsigned __int64 result; // rax
  char *v3; // rbx
  __int64 v4; // rcx
  __int64 v5; // rdx
  unsigned __int64 v6; // rcx
  PWSTR v7; // rdi
  PWSTR Buffer; // rcx
  UNICODE_STRING String1; // [rsp+20h] [rbp-18h] BYREF

  *(_DWORD *)(&String1.MaximumLength + 1) = 0;
  String1.MaximumLength = a2;
  String1.Buffer = a1;
  result = String2.Length;
  String1.Length = String2.Length;
  if ( String2.Length > 2u )
  {
    v3 = (char *)a1 + a2;
    while ( 1 )
    {
      result += (unsigned __int64)a1;
      if ( result >= (unsigned __int64)v3 )
        break;
      if ( RtlEqualUnicodeString(&String1, &String2, 1u) )
      {
        v4 = String2.Length >> 1;
        v5 = (unsigned int)v4;
        if ( (int)v4 - 2 >= 1 )
        {
          v6 = (unsigned __int64)(2 * v4 - 4) >> 1;
          v7 = String1.Buffer + 1;
          while ( v6 )
          {
            *v7++ = 42;
            --v6;
          }
        }
        Buffer = &String1.Buffer[v5 - 2];
      }
      else
      {
        Buffer = String1.Buffer;
      }
      a1 = Buffer + 1;
      String1.MaximumLength -= 2;
      result = String2.Length;
      String1.Buffer = a1;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001ae98  mov     rax, rsp
0x18001ae9b  mov     [rax+8], rbx
0x18001ae9f  mov     [rax+10h], rsi
0x18001aea3  push    rdi
0x18001aea4  sub     rsp, 30h
0x18001aea8  mov     dword ptr [rax-14h], 0
0x18001aeaf  mov     esi, 2
0x18001aeb4  mov     [rax-16h], dx
0x18001aeb8  mov     [rax-10h], rcx
0x18001aebc  movzx   eax, cs:String2.Length
0x18001aec3  mov     [rsp+38h+String1.Length], ax
0x18001aec8  cmp     ax, si
0x18001aecb  jbe     loc_18001AF62
0x18001aed1  movzx   ebx, dx
0x18001aed4  add     rbx, rcx
0x18001aed7  jmp     short loc_18001AF56
0x18001aed9  mov     r8b, 1; CaseInsensitive
0x18001aedc  lea     rdx, String2; String2
0x18001aee3  lea     rcx, [rsp+38h+String1]; String1
0x18001aee8  call    cs:__imp_RtlEqualUnicodeString
0x18001aeef  nop     dword ptr [rax+rax+00h]
0x18001aef4  test    al, al
0x18001aef6  jz      short loc_18001AF38
0x18001aef8  movzx   ecx, cs:String2.Length
0x18001aeff  shr     ecx, 1
0x18001af01  mov     edx, ecx
0x18001af03  lea     eax, [rcx-2]
0x18001af06  cmp     eax, 1
0x18001af09  jl      short loc_18001AF29
0x18001af0b  mov     rdi, [rsp+38h+String1.Buffer]
0x18001af10  lea     rcx, ds:0FFFFFFFFFFFFFFFCh[rcx*2]
0x18001af18  shr     rcx, 1
0x18001af1b  mov     eax, 2Ah ; '*'
0x18001af20  add     rdi, rsi
0x18001af23  movzx   eax, ax
0x18001af26  rep stosw
0x18001af29  mov     rcx, [rsp+38h+String1.Buffer]
0x18001af2e  add     rcx, 0FFFFFFFFFFFFFFFCh
0x18001af32  lea     rcx, [rcx+rdx*2]
0x18001af36  jmp     short loc_18001AF3D
0x18001af38  mov     rcx, [rsp+38h+String1.Buffer]
0x18001af3d  add     rcx, rsi
0x18001af40  mov     eax, 0FFFEh
0x18001af45  add     [rsp+38h+String1.MaximumLength], ax
0x18001af4a  movzx   eax, cs:String2.Length
0x18001af51  mov     [rsp+38h+String1.Buffer], rcx
0x18001af56  add     rax, rcx
0x18001af59  cmp     rax, rbx
0x18001af5c  jb      loc_18001AED9
0x18001af62  mov     rbx, [rsp+38h+arg_0]
0x18001af67  mov     rsi, [rsp+38h+arg_8]
0x18001af6c  add     rsp, 30h
0x18001af70  pop     rdi
0x18001af71  retn
```
