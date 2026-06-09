# CMValLink

- ea: `0x18001dc78`
- end: `0x18001dd5e`
- name: `CMValLink`
- size: `230`
- prototype: `__int64 __fastcall(HPROFILE hProfile)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800061dc`

## callees

- `0x18001db20`
- `0x18001dc78`

## import_xrefs

- `mscms!IsColorProfileTagPresent` at `0x18001dca0`
- `mscms!IsColorProfileTagPresent` at `0x18001dcc6`
- `mscms!IsColorProfileTagPresent` at `0x18001dce8`
- `mscms!IsColorProfileTagPresent` at `0x18001dd0a`
- `mscms!IsColorProfileTagPresent` at `0x18001dd41`
- `mscms!IsColorProfileTagPresent` at `0x18001dca0`
- `mscms!IsColorProfileTagPresent` at `0x18001dcc6`
- `mscms!IsColorProfileTagPresent` at `0x18001dce8`
- `mscms!IsColorProfileTagPresent` at `0x18001dd0a`
- `mscms!IsColorProfileTagPresent` at `0x18001dd41`

## pseudocode

```c
char __fastcall CMValLink(HPROFILE hProfile, __int64 a2)
{
  char v4; // r8
  WINBOOL pbPresent; // [rsp+40h] [rbp+20h] BYREF

  pbPresent = 0;
  IsColorProfileTagPresent(hProfile, 0x64657363u, &pbPresent);
  v4 = pbPresent;
  if ( (_BYTE)pbPresent )
  {
    pbPresent = 0;
    IsColorProfileTagPresent(hProfile, 0x41324230u, &pbPresent);
    v4 = pbPresent;
    if ( (_BYTE)pbPresent )
    {
      pbPresent = 0;
      IsColorProfileTagPresent(hProfile, 0x70736571u, &pbPresent);
      v4 = pbPresent;
      if ( (_BYTE)pbPresent )
      {
        pbPresent = 0;
        IsColorProfileTagPresent(hProfile, 0x63707274u, &pbPresent);
        v4 = pbPresent;
        if ( (_BYTE)pbPresent )
        {
          if ( *(_DWORD *)(a2 + 8) >= 0x4000000u && (unsigned __int8)CMColorSpaceIsNColor(*(unsigned int *)(a2 + 16)) )
          {
            pbPresent = 0;
            IsColorProfileTagPresent(hProfile, 0x636C7274u, &pbPresent);
            return pbPresent;
          }
        }
      }
    }
  }
  return v4;
}

```

## disassembly

```asm
0x18001dc78  mov     [rsp-8+arg_0], rbx
0x18001dc7d  mov     [rsp-8+arg_8], rdi
0x18001dc82  push    rbp
0x18001dc83  mov     rbp, rsp
0x18001dc86  sub     rsp, 20h
0x18001dc8a  mov     rdi, rdx
0x18001dc8d  mov     [rbp+pbPresent], 0
0x18001dc94  mov     edx, 64657363h; tag
0x18001dc99  lea     r8, [rbp+pbPresent]; pbPresent
0x18001dc9d  mov     rbx, rcx
0x18001dca0  call    cs:__imp_IsColorProfileTagPresent
0x18001dca6  mov     r8b, byte ptr [rbp+pbPresent]
0x18001dcaa  test    r8b, r8b
0x18001dcad  jz      loc_18001DD4B
0x18001dcb3  lea     r8, [rbp+pbPresent]; pbPresent
0x18001dcb7  mov     [rbp+pbPresent], 0
0x18001dcbe  mov     edx, 41324230h; tag
0x18001dcc3  mov     rcx, rbx; hProfile
0x18001dcc6  call    cs:__imp_IsColorProfileTagPresent
0x18001dccc  mov     r8b, byte ptr [rbp+pbPresent]
0x18001dcd0  test    r8b, r8b
0x18001dcd3  jz      short loc_18001DD4B
0x18001dcd5  lea     r8, [rbp+pbPresent]; pbPresent
0x18001dcd9  mov     [rbp+pbPresent], 0
0x18001dce0  mov     edx, 70736571h; tag
0x18001dce5  mov     rcx, rbx; hProfile
0x18001dce8  call    cs:__imp_IsColorProfileTagPresent
0x18001dcee  mov     r8b, byte ptr [rbp+pbPresent]
0x18001dcf2  test    r8b, r8b
0x18001dcf5  jz      short loc_18001DD4B
0x18001dcf7  lea     r8, [rbp+pbPresent]; pbPresent
0x18001dcfb  mov     [rbp+pbPresent], 0
0x18001dd02  mov     edx, 63707274h; tag
0x18001dd07  mov     rcx, rbx; hProfile
0x18001dd0a  call    cs:__imp_IsColorProfileTagPresent
0x18001dd10  mov     r8b, byte ptr [rbp+pbPresent]
0x18001dd14  test    r8b, r8b
0x18001dd17  jz      short loc_18001DD4B
0x18001dd19  cmp     dword ptr [rdi+8], 4000000h
0x18001dd20  jb      short loc_18001DD4B
0x18001dd22  mov     ecx, [rdi+10h]
0x18001dd25  call    CMColorSpaceIsNColor
0x18001dd2a  test    al, al
0x18001dd2c  jz      short loc_18001DD4B
0x18001dd2e  lea     r8, [rbp+pbPresent]; pbPresent
0x18001dd32  mov     [rbp+pbPresent], 0
0x18001dd39  mov     edx, 636C7274h; tag
0x18001dd3e  mov     rcx, rbx; hProfile
0x18001dd41  call    cs:__imp_IsColorProfileTagPresent
0x18001dd47  mov     r8b, byte ptr [rbp+pbPresent]
0x18001dd4b  mov     rbx, [rsp+20h+arg_0]
0x18001dd50  mov     al, r8b
0x18001dd53  mov     rdi, [rsp+20h+arg_8]
0x18001dd58  add     rsp, 20h
0x18001dd5c  pop     rbp
0x18001dd5d  retn
```
