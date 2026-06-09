# LpkCheckForMirrorSignature(void)

- ea: `0x1800465e0`
- end: `0x180046758`
- name: `?LpkCheckForMirrorSignature@@YAHXZ`
- size: `376`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180046570`

## callees

- `0x1800465e0`
- `0x18007f800`

## import_xrefs

- `ntdll!LdrFindResourceEx_U` at `0x180046663`
- `ntdll!LdrFindResourceEx_U` at `0x180046663`
- `ntdll!LdrAccessResource` at `0x180046688`
- `ntdll!LdrAccessResource` at `0x180046688`
- `USER32!SetProcessDefaultLayout` at `0x180046746`
- `USER32!SetProcessDefaultLayout` at `0x180046746`

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
0x1800465e0  push    rbp
0x1800465e2  push    rbx
0x1800465e3  push    rsi
0x1800465e4  push    rdi
0x1800465e5  lea     rbp, [rsp-3Fh]
0x1800465ea  sub     rsp, 98h
0x1800465f1  mov     rax, cs:__security_cookie
0x1800465f8  xor     rax, rsp
0x1800465fb  mov     [rbp+57h+var_30], rax
0x1800465ff  movups  xmm0, xmmword ptr cs:aFiledescriptio; "FileDescription"
0x180046606  xor     esi, esi
0x180046608  movups  xmm1, xmmword ptr cs:aFiledescriptio+10h; "ription"
0x18004660f  mov     [rbp+57h+Resource], rsi
0x180046613  mov     [rbp+57h+ResourceDataEntry], rsi
0x180046617  mov     [rbp+57h+Size], esi
0x18004661a  mov     rax, gs:60h
0x180046623  movups  [rbp+57h+var_68], xmm0
0x180046627  movups  [rbp+57h+var_58], xmm1
0x18004662b  mov     rdi, [rax+10h]
0x18004662f  test    rdi, rdi
0x180046632  jz      loc_180046754
0x180046638  lea     rax, [rbp+57h+ResourceDataEntry]
0x18004663c  mov     [rbp+57h+var_48], 10h
0x180046644  lea     r9d, [rsi+3]
0x180046648  mov     [rsp+0B0h+var_90], rax
0x18004664d  lea     r8, [rbp+57h+var_48]
0x180046651  mov     [rbp+57h+var_40], 1
0x180046659  mov     rdx, rdi
0x18004665c  mov     [rbp+57h+var_38], rsi
0x180046660  lea     ecx, [rsi+8]
0x180046663  call    cs:__imp_LdrFindResourceEx_U
0x18004666a  nop     dword ptr [rax+rax+00h]
0x18004666f  mov     ebx, eax
0x180046671  test    eax, eax
0x180046673  js      loc_180046711
0x180046679  mov     rdx, [rbp+57h+ResourceDataEntry]; ResourceDataEntry
0x18004667d  lea     r9, [rbp+57h+Size]; Size
0x180046681  lea     r8, [rbp+57h+Resource]; Resource
0x180046685  mov     rcx, rdi; BaseAddress
0x180046688  call    cs:__imp_LdrAccessResource
0x18004668f  nop     dword ptr [rax+rax+00h]
0x180046694  mov     ebx, eax
0x180046696  test    eax, eax
0x180046698  js      short loc_180046711
0x18004669a  mov     r9d, [rbp+57h+Size]
0x18004669e  shr     r9d, 1
0x1800466a1  cmp     r9d, 10h
0x1800466a5  jb      short loc_180046711
0x1800466a7  mov     r10, [rbp+57h+Resource]
0x1800466ab  mov     edx, esi
0x1800466ad  mov     r8d, esi
0x1800466b0  cmp     edx, r9d
0x1800466b3  jnb     short loc_180046711
0x1800466b5  mov     eax, edx
0x1800466b7  mov     ecx, r8d
0x1800466ba  movzx   eax, word ptr [r10+rax*2]
0x1800466bf  cmp     word ptr [rbp+rcx*2+57h+var_68], ax
0x1800466c4  jz      short loc_1800466CA
0x1800466c6  inc     edx
0x1800466c8  jmp     short loc_1800466B0
0x1800466ca  mov     eax, r9d
0x1800466cd  sub     eax, edx
0x1800466cf  inc     eax
0x1800466d1  cmp     eax, 10h
0x1800466d4  jb      short loc_1800466C6
0x1800466d6  mov     eax, edx
0x1800466d8  cmp     r8d, 10h
0x1800466dc  jnb     short loc_1800466F4
0x1800466de  movzx   eax, word ptr [r10+rax*2]
0x1800466e3  mov     ecx, r8d
0x1800466e6  cmp     word ptr [rbp+rcx*2+57h+var_68], ax
0x1800466eb  jnz     short loc_1800466AD
0x1800466ed  inc     r8d
0x1800466f0  inc     edx
0x1800466f2  jmp     short loc_1800466D6
0x1800466f4  jnz     short loc_1800466B0
0x1800466f6  cmp     [r10+rax*2], si
0x1800466fb  jnz     short loc_180046706
0x1800466fd  inc     edx
0x1800466ff  cmp     [r10+rdx*2], si
0x180046704  jz      short loc_1800466FD
0x180046706  mov     eax, edx
0x180046708  lea     rdx, [r10+rax*2]
0x18004670c  test    rdx, rdx
0x18004670f  jnz     short loc_180046731
0x180046711  not     ebx
0x180046713  shr     ebx, 1Fh
0x180046716  mov     eax, ebx
0x180046718  mov     rcx, [rbp+57h+var_30]
0x18004671c  xor     rcx, rsp; StackCookie
0x18004671f  call    __security_check_cookie
0x180046724  add     rsp, 98h
0x18004672b  pop     rdi
0x18004672c  pop     rsi
0x18004672d  pop     rbx
0x18004672e  pop     rbp
0x18004672f  retn
0x180046731  mov     eax, 200Eh
0x180046736  cmp     ax, [rdx]
0x180046739  jnz     short loc_180046711
0x18004673b  cmp     ax, [rdx+2]
0x18004673f  jnz     short loc_180046711
0x180046741  mov     ecx, 1; dwDefaultLayout
0x180046746  call    cs:__imp_SetProcessDefaultLayout
0x18004674d  nop     dword ptr [rax+rax+00h]
0x180046752  jmp     short loc_180046711
0x180046754  xor     eax, eax
0x180046756  jmp     short loc_180046718
```
