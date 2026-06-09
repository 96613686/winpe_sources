# LpkCheckForMirrorSignature(void)

- ea: `0x18003aa88`
- end: `0x18003abed`
- name: `?LpkCheckForMirrorSignature@@YAHXZ`
- size: `357`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18003aa20`

## callees

- `0x18003aa88`
- `0x18007ac50`

## import_xrefs

- `ntdll!LdrFindResourceEx_U` at `0x18003ab0b`
- `ntdll!LdrFindResourceEx_U` at `0x18003ab0b`
- `ntdll!LdrAccessResource` at `0x18003ab2a`
- `ntdll!LdrAccessResource` at `0x18003ab2a`
- `USER32!SetProcessDefaultLayout` at `0x18003abe1`
- `USER32!SetProcessDefaultLayout` at `0x18003abe1`

## pseudocode

```c
_BOOL8 LpkCheckForMirrorSignature(void)
{
  PVOID ImageBaseAddress; // rdi
  NTSTATUS v1; // ebx
  ULONG v2; // r9d
  __int64 v3; // rdx
  unsigned int v4; // r8d
  _WORD *v5; // rdx
  ULONG Size; // [rsp+30h] [rbp-29h] BYREF
  PIMAGE_RESOURCE_DATA_ENTRY ResourceDataEntry; // [rsp+38h] [rbp-21h] BYREF
  PVOID Resource; // [rsp+40h] [rbp-19h] BYREF
  _OWORD v10[2]; // [rsp+48h] [rbp-11h]
  _QWORD v11[3]; // [rsp+68h] [rbp+Fh] BYREF

  Resource = 0;
  ResourceDataEntry = 0;
  Size = 0;
  v10[0] = *(_OWORD *)L"FileDescription";
  v10[1] = *(_OWORD *)L"ription";
  ImageBaseAddress = NtCurrentPeb()->ImageBaseAddress;
  if ( !ImageBaseAddress )
    return 0;
  v11[0] = 16;
  v11[1] = 1;
  v11[2] = 0;
  v1 = LdrFindResourceEx_U(8, ImageBaseAddress, v11, 3, &ResourceDataEntry);
  if ( v1 >= 0 )
  {
    v1 = LdrAccessResource(ImageBaseAddress, ResourceDataEntry, &Resource, &Size);
    if ( v1 >= 0 )
    {
      v2 = Size >> 1;
      if ( Size >> 1 >= 0x10 )
      {
        LODWORD(v3) = 0;
LABEL_6:
        v4 = 0;
        while ( (unsigned int)v3 < v2 )
        {
          if ( *((_WORD *)v10 + v4) == *((_WORD *)Resource + (unsigned int)v3) && v2 - (unsigned int)v3 + 1 >= 0x10 )
          {
            while ( v4 < 0x10 )
            {
              if ( *((_WORD *)v10 + v4) != *((_WORD *)Resource + (unsigned int)v3) )
                goto LABEL_6;
              ++v4;
              LODWORD(v3) = v3 + 1;
            }
            if ( v4 == 16 )
            {
              if ( !*((_WORD *)Resource + (unsigned int)v3) )
              {
                do
                  v3 = (unsigned int)(v3 + 1);
                while ( !*((_WORD *)Resource + v3) );
              }
              v5 = (char *)Resource + 2 * (unsigned int)v3;
              if ( v5 && *v5 == 8206 && v5[1] == 8206 )
                SetProcessDefaultLayout(1u);
              return v1 >= 0;
            }
          }
          else
          {
            LODWORD(v3) = v3 + 1;
          }
        }
      }
    }
  }
  return v1 >= 0;
}

```

## disassembly

```asm
0x18003aa88  push    rbp
0x18003aa8a  push    rbx
0x18003aa8b  push    rsi
0x18003aa8c  push    rdi
0x18003aa8d  lea     rbp, [rsp-3Fh]
0x18003aa92  sub     rsp, 98h
0x18003aa99  mov     rax, cs:__security_cookie
0x18003aaa0  xor     rax, rsp
0x18003aaa3  mov     [rbp+57h+var_30], rax
0x18003aaa7  movups  xmm0, xmmword ptr cs:aFiledescriptio; "FileDescription"
0x18003aaae  xor     esi, esi
0x18003aab0  movups  xmm1, xmmword ptr cs:aFiledescriptio+10h; "ription"
0x18003aab7  mov     [rbp+57h+Resource], rsi
0x18003aabb  mov     [rbp+57h+ResourceDataEntry], rsi
0x18003aabf  mov     [rbp+57h+Size], esi
0x18003aac2  mov     rax, gs:60h
0x18003aacb  movups  [rbp+57h+var_68], xmm0
0x18003aacf  movups  [rbp+57h+var_58], xmm1
0x18003aad3  mov     rdi, [rax+10h]
0x18003aad7  test    rdi, rdi
0x18003aada  jz      loc_18003ABE9
0x18003aae0  lea     rax, [rbp+57h+ResourceDataEntry]
0x18003aae4  mov     [rbp+57h+var_48], 10h
0x18003aaec  lea     r9d, [rsi+3]
0x18003aaf0  mov     [rsp+0B0h+var_90], rax
0x18003aaf5  lea     r8, [rbp+57h+var_48]
0x18003aaf9  mov     [rbp+57h+var_40], 1
0x18003ab01  mov     rdx, rdi
0x18003ab04  mov     [rbp+57h+var_38], rsi
0x18003ab08  lea     ecx, [rsi+8]
0x18003ab0b  call    cs:__imp_LdrFindResourceEx_U
0x18003ab11  mov     ebx, eax
0x18003ab13  test    eax, eax
0x18003ab15  js      loc_18003ABAD
0x18003ab1b  mov     rdx, [rbp+57h+ResourceDataEntry]; ResourceDataEntry
0x18003ab1f  lea     r9, [rbp+57h+Size]; Size
0x18003ab23  lea     r8, [rbp+57h+Resource]; Resource
0x18003ab27  mov     rcx, rdi; BaseAddress
0x18003ab2a  call    cs:__imp_LdrAccessResource
0x18003ab30  mov     ebx, eax
0x18003ab32  test    eax, eax
0x18003ab34  js      short loc_18003ABAD
0x18003ab36  mov     r9d, [rbp+57h+Size]
0x18003ab3a  shr     r9d, 1
0x18003ab3d  cmp     r9d, 10h
0x18003ab41  jb      short loc_18003ABAD
0x18003ab43  mov     r10, [rbp+57h+Resource]
0x18003ab47  mov     edx, esi
0x18003ab49  mov     r8d, esi
0x18003ab4c  cmp     edx, r9d
0x18003ab4f  jnb     short loc_18003ABAD
0x18003ab51  mov     eax, edx
0x18003ab53  mov     ecx, r8d
0x18003ab56  movzx   eax, word ptr [r10+rax*2]
0x18003ab5b  cmp     word ptr [rbp+rcx*2+57h+var_68], ax
0x18003ab60  jz      short loc_18003AB66
0x18003ab62  inc     edx
0x18003ab64  jmp     short loc_18003AB4C
0x18003ab66  mov     eax, r9d
0x18003ab69  sub     eax, edx
0x18003ab6b  inc     eax
0x18003ab6d  cmp     eax, 10h
0x18003ab70  jb      short loc_18003AB62
0x18003ab72  mov     eax, edx
0x18003ab74  cmp     r8d, 10h
0x18003ab78  jnb     short loc_18003AB90
0x18003ab7a  movzx   eax, word ptr [r10+rax*2]
0x18003ab7f  mov     ecx, r8d
0x18003ab82  cmp     word ptr [rbp+rcx*2+57h+var_68], ax
0x18003ab87  jnz     short loc_18003AB49
0x18003ab89  inc     r8d
0x18003ab8c  inc     edx
0x18003ab8e  jmp     short loc_18003AB72
0x18003ab90  jnz     short loc_18003AB4C
0x18003ab92  cmp     [r10+rax*2], si
0x18003ab97  jnz     short loc_18003ABA2
0x18003ab99  inc     edx
0x18003ab9b  cmp     [r10+rdx*2], si
0x18003aba0  jz      short loc_18003AB99
0x18003aba2  mov     eax, edx
0x18003aba4  lea     rdx, [r10+rax*2]
0x18003aba8  test    rdx, rdx
0x18003abab  jnz     short loc_18003ABCC
0x18003abad  not     ebx
0x18003abaf  shr     ebx, 1Fh
0x18003abb2  mov     eax, ebx
0x18003abb4  mov     rcx, [rbp+57h+var_30]
0x18003abb8  xor     rcx, rsp; StackCookie
0x18003abbb  call    __security_check_cookie
0x18003abc0  add     rsp, 98h
0x18003abc7  pop     rdi
0x18003abc8  pop     rsi
0x18003abc9  pop     rbx
0x18003abca  pop     rbp
0x18003abcb  retn
0x18003abcc  mov     eax, 200Eh
0x18003abd1  cmp     ax, [rdx]
0x18003abd4  jnz     short loc_18003ABAD
0x18003abd6  cmp     ax, [rdx+2]
0x18003abda  jnz     short loc_18003ABAD
0x18003abdc  mov     ecx, 1; dwDefaultLayout
0x18003abe1  call    cs:__imp_SetProcessDefaultLayout
0x18003abe7  jmp     short loc_18003ABAD
0x18003abe9  xor     eax, eax
0x18003abeb  jmp     short loc_18003ABB4
```
