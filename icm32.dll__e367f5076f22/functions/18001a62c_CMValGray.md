# CMValGray

- ea: `0x18001a62c`
- end: `0x18001a6c0`
- name: `CMValGray`
- size: `148`
- prototype: `__int64 __fastcall(HPROFILE hProfile)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180006340`
- `0x180007e98`
- `0x18001a538`

## callees

- `0x18001a62c`

## import_xrefs

- `mscms!IsColorProfileTagPresent` at `0x18001a64c`
- `mscms!IsColorProfileTagPresent` at `0x18001a66c`
- `mscms!IsColorProfileTagPresent` at `0x18001a68c`
- `mscms!IsColorProfileTagPresent` at `0x18001a6ac`
- `mscms!IsColorProfileTagPresent` at `0x18001a64c`
- `mscms!IsColorProfileTagPresent` at `0x18001a66c`
- `mscms!IsColorProfileTagPresent` at `0x18001a68c`
- `mscms!IsColorProfileTagPresent` at `0x18001a6ac`

## pseudocode

```c
char __fastcall CMValGray(HPROFILE hProfile)
{
  char result; // al
  WINBOOL pbPresent; // [rsp+38h] [rbp+18h] BYREF

  pbPresent = 0;
  IsColorProfileTagPresent(hProfile, 0x64657363u, &pbPresent);
  result = pbPresent;
  if ( (_BYTE)pbPresent )
  {
    pbPresent = 0;
    IsColorProfileTagPresent(hProfile, 0x6B545243u, &pbPresent);
    result = pbPresent;
    if ( (_BYTE)pbPresent )
    {
      pbPresent = 0;
      IsColorProfileTagPresent(hProfile, 0x77747074u, &pbPresent);
      result = pbPresent;
      if ( (_BYTE)pbPresent )
      {
        pbPresent = 0;
        IsColorProfileTagPresent(hProfile, 0x63707274u, &pbPresent);
        return pbPresent;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001a62c  mov     [rsp-8+arg_0], rbx
0x18001a631  push    rbp
0x18001a632  mov     rbp, rsp
0x18001a635  sub     rsp, 20h
0x18001a639  lea     r8, [rbp+pbPresent]; pbPresent
0x18001a63d  mov     [rbp+pbPresent], 0
0x18001a644  mov     edx, 64657363h; tag
0x18001a649  mov     rbx, rcx
0x18001a64c  call    cs:__imp_IsColorProfileTagPresent
0x18001a652  mov     al, byte ptr [rbp+pbPresent]
0x18001a655  test    al, al
0x18001a657  jz      short loc_18001A6B5
0x18001a659  lea     r8, [rbp+pbPresent]; pbPresent
0x18001a65d  mov     [rbp+pbPresent], 0
0x18001a664  mov     edx, 6B545243h; tag
0x18001a669  mov     rcx, rbx; hProfile
0x18001a66c  call    cs:__imp_IsColorProfileTagPresent
0x18001a672  mov     al, byte ptr [rbp+pbPresent]
0x18001a675  test    al, al
0x18001a677  jz      short loc_18001A6B5
0x18001a679  lea     r8, [rbp+pbPresent]; pbPresent
0x18001a67d  mov     [rbp+pbPresent], 0
0x18001a684  mov     edx, 77747074h; tag
0x18001a689  mov     rcx, rbx; hProfile
0x18001a68c  call    cs:__imp_IsColorProfileTagPresent
0x18001a692  mov     al, byte ptr [rbp+pbPresent]
0x18001a695  test    al, al
0x18001a697  jz      short loc_18001A6B5
0x18001a699  lea     r8, [rbp+pbPresent]; pbPresent
0x18001a69d  mov     [rbp+pbPresent], 0
0x18001a6a4  mov     edx, 63707274h; tag
0x18001a6a9  mov     rcx, rbx; hProfile
0x18001a6ac  call    cs:__imp_IsColorProfileTagPresent
0x18001a6b2  mov     al, byte ptr [rbp+pbPresent]
0x18001a6b5  mov     rbx, [rsp+20h+arg_0]
0x18001a6ba  add     rsp, 20h
0x18001a6be  pop     rbp
0x18001a6bf  retn
```
