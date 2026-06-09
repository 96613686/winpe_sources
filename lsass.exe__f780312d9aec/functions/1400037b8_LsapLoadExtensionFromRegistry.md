# LsapLoadExtensionFromRegistry

- ea: `0x1400037b8`
- end: `0x1400038c5`
- name: `LsapLoadExtensionFromRegistry`
- size: `269`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x1400038cc`

## callees

- `0x1400016c0`
- `0x140001a80`
- `0x140003654`
- `0x1400037b8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1400037f9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140003859`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1400037f9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140003859`

## string_xrefs

- `0x1400037e0`: `Extension`
- `0x14000384a`: `Extension`

## pseudocode

```c
__int64 __fastcall LsapLoadExtensionFromRegistry(HKEY hKey, __int64 *a2)
{
  __int64 v4; // rdx
  ULONG Extension; // ebx
  __int64 v6; // r8
  BYTE *lpData; // rdi
  DWORD cbData; // [rsp+58h] [rbp+10h] BYREF
  DWORD Type; // [rsp+60h] [rbp+18h] BYREF

  *a2 = 0;
  Type = 0;
  cbData = 0;
  Extension = RegQueryValueExW(hKey, L"Extension", 0, &Type, 0, &cbData);
  if ( !Extension )
  {
    if ( cbData <= 2 || (cbData & 0xFFFFFFFE) >= 0x208 )
    {
      return 87;
    }
    else
    {
      lpData = (BYTE *)LsapAllocateLsaHeap(cbData, v4, v6);
      if ( lpData )
      {
        Extension = RegQueryValueExW(hKey, L"Extension", 0, &Type, lpData, &cbData);
        if ( !Extension )
        {
          if ( Type == 1 )
          {
            if ( (cbData >> 1) - 2 > 0x101 || *(_WORD *)&lpData[2 * (cbData >> 1) - 2] )
              Extension = 13;
            else
              Extension = LsapLoadExtension(lpData, a2);
          }
          else
          {
            Extension = 1804;
          }
        }
        LsapFreeLsaHeap(lpData);
      }
      else
      {
        return 8;
      }
    }
  }
  return Extension;
}

```

## disassembly

```asm
0x1400037b8  mov     r11, rsp
0x1400037bb  mov     [r11+8], rbx
0x1400037bf  mov     [r11+20h], rbp
0x1400037c3  push    rsi
0x1400037c4  push    rdi
0x1400037c5  push    r14
0x1400037c7  sub     rsp, 30h
0x1400037cb  xor     r14d, r14d
0x1400037ce  lea     rax, [r11+10h]
0x1400037d2  mov     [rdx], r14
0x1400037d5  lea     r9, [r11+18h]; lpType
0x1400037d9  mov     rsi, rdx
0x1400037dc  mov     [r11-20h], rax
0x1400037e0  lea     rdx, ValueName; "Extension"
0x1400037e7  mov     [r11+18h], r14d
0x1400037eb  xor     r8d, r8d; lpReserved
0x1400037ee  mov     [r11+10h], r14d
0x1400037f2  mov     rbp, rcx
0x1400037f5  mov     [r11-28h], r14
0x1400037f9  call    cs:__imp_RegQueryValueExW
0x1400037ff  mov     ebx, eax
0x140003801  test    eax, eax
0x140003803  jnz     loc_1400038B0
0x140003809  mov     ecx, [rsp+48h+cbData]
0x14000380d  cmp     ecx, 2
0x140003810  jbe     loc_1400038AB
0x140003816  mov     eax, ecx
0x140003818  and     eax, 0FFFFFFFEh
0x14000381b  cmp     eax, 208h
0x140003820  jnb     loc_1400038AB
0x140003826  call    LsapAllocateLsaHeap
0x14000382b  mov     rdi, rax
0x14000382e  test    rax, rax
0x140003831  jnz     short loc_140003838
0x140003833  lea     ebx, [rax+8]
0x140003836  jmp     short loc_1400038B0
0x140003838  lea     rax, [rsp+48h+cbData]
0x14000383d  xor     r8d, r8d; lpReserved
0x140003840  mov     [rsp+48h+lpcbData], rax; lpcbData
0x140003845  lea     r9, [rsp+48h+Type]; lpType
0x14000384a  lea     rdx, ValueName; "Extension"
0x140003851  mov     [rsp+48h+lpData], rdi; lpData
0x140003856  mov     rcx, rbp; hKey
0x140003859  call    cs:__imp_RegQueryValueExW
0x14000385f  mov     ebx, eax
0x140003861  test    eax, eax
0x140003863  jnz     short loc_1400038A1
0x140003865  cmp     [rsp+48h+Type], 1
0x14000386a  jz      short loc_140003873
0x14000386c  mov     ebx, 70Ch
0x140003871  jmp     short loc_1400038A1
0x140003873  mov     ecx, [rsp+48h+cbData]
0x140003877  shr     ecx, 1
0x140003879  lea     eax, [rcx-2]
0x14000387c  cmp     eax, 101h
0x140003881  ja      short loc_14000389C
0x140003883  lea     eax, [rcx-1]
0x140003886  cmp     [rdi+rax*2], r14w
0x14000388b  jnz     short loc_14000389C
0x14000388d  mov     rdx, rsi
0x140003890  mov     rcx, rdi; Src
0x140003893  call    LsapLoadExtension
0x140003898  mov     ebx, eax
0x14000389a  jmp     short loc_1400038A1
0x14000389c  mov     ebx, 0Dh
0x1400038a1  mov     rcx, rdi
0x1400038a4  call    LsapFreeLsaHeap
0x1400038a9  jmp     short loc_1400038B0
0x1400038ab  mov     ebx, 57h ; 'W'
0x1400038b0  mov     rbp, [rsp+48h+arg_18]
0x1400038b5  mov     eax, ebx
0x1400038b7  mov     rbx, [rsp+48h+arg_0]
0x1400038bc  add     rsp, 30h
0x1400038c0  pop     r14
0x1400038c2  pop     rdi
0x1400038c3  pop     rsi
0x1400038c4  retn
```
