# PsmpAppIdentityValidateEx

- ea: `0x18001d34c`
- end: `0x18001d3b2`
- name: `PsmpAppIdentityValidateEx`
- size: `102`
- prototype: `__int64 __fastcall(PSID Sid, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180019670`

## callees

- `0x180013844`
- `0x18001d34c`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x18001d386`
- `ntdll!RtlLengthSid` at `0x18001d386`
- `ntdll!RtlValidSid` at `0x18001d372`
- `ntdll!RtlValidSid` at `0x18001d372`

## pseudocode

```c
__int64 __fastcall PsmpAppIdentityValidateEx(PSID Sid, __int64 a2, __int64 a3)
{
  int v4; // ebx
  __int64 result; // rax
  char v6; // [rsp+48h] [rbp+20h] BYREF

  v4 = a2;
  result = RtlStringCchLengthW(a3, a2, &v6);
  if ( (int)result >= 0 )
  {
    if ( RtlValidSid(Sid) && RtlLengthSid(Sid) <= 0x44 )
    {
      if ( (v4 & 0xFFFFFFF3) != 0 || v4 == 12 )
        return 3221225713LL;
      else
        return 0;
    }
    else
    {
      return 3221225711LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001d34c  mov     [rsp+arg_0], rbx
0x18001d351  push    rdi
0x18001d352  sub     rsp, 20h
0x18001d356  mov     rax, r8
0x18001d359  mov     rdi, rcx
0x18001d35c  mov     rcx, rax
0x18001d35f  lea     r8, [rsp+28h+arg_18]
0x18001d364  mov     ebx, edx
0x18001d366  call    RtlStringCchLengthW
0x18001d36b  test    eax, eax
0x18001d36d  js      short loc_18001D3A7
0x18001d36f  mov     rcx, rdi; Sid
0x18001d372  call    cs:__imp_RtlValidSid
0x18001d378  test    al, al
0x18001d37a  jnz     short loc_18001D383
0x18001d37c  mov     eax, 0C00000EFh
0x18001d381  jmp     short loc_18001D3A7
0x18001d383  mov     rcx, rdi; Sid
0x18001d386  call    cs:__imp_RtlLengthSid
0x18001d38c  cmp     eax, 44h ; 'D'
0x18001d38f  ja      short loc_18001D37C
0x18001d391  test    ebx, 0FFFFFFF3h
0x18001d397  jnz     short loc_18001D3A2
0x18001d399  cmp     ebx, 0Ch
0x18001d39c  jz      short loc_18001D3A2
0x18001d39e  xor     eax, eax
0x18001d3a0  jmp     short loc_18001D3A7
0x18001d3a2  mov     eax, 0C00000F1h
0x18001d3a7  mov     rbx, [rsp+28h+arg_0]
0x18001d3ac  add     rsp, 20h
0x18001d3b0  pop     rdi
0x18001d3b1  retn
```
