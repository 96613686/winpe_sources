# CMValidateProfile

- ea: `0x1800061dc`
- end: `0x180006339`
- name: `CMValidateProfile`
- size: `349`
- prototype: `__int64 __fastcall(HPROFILE hProfile, _BYTE *)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x180005974`
- `0x1800061b0`

## callees

- `0x1800061dc`
- `0x180006340`
- `0x180007e98`
- `0x18001a538`
- `0x18001c8a0`
- `0x18001dba4`
- `0x18001dc78`
- `0x18001dd64`
- `0x18003d00e`
- `0x18003d040`

## import_xrefs

- `mscms!GetColorProfileHeader` at `0x180006224`
- `mscms!GetColorProfileHeader` at `0x180006224`

## pseudocode

```c
__int64 __fastcall CMValidateProfile(HPROFILE hProfile, _BYTE *a2)
{
  unsigned int v4; // edi
  BOOL ColorProfileHeader; // eax
  char v7; // al
  PROFILEHEADER pHeader; // [rsp+20h] [rbp-49h] BYREF

  memset_0(&pHeader, 0, sizeof(pHeader));
  *a2 = 0;
  v4 = 2011;
  ColorProfileHeader = GetColorProfileHeader(hProfile, &pHeader);
  if ( pHeader.phSignature == 1633907568 && ColorProfileHeader )
  {
    if ( (pHeader.phVersion & 0xFF000000) - 0x2000000 > 0x2000000 || (pHeader.phVersion & 0xFF000000) == 0x3000000 )
    {
      *a2 = 0;
      return v4;
    }
    v4 = 0;
    switch ( pHeader.phClass )
    {
      case 0x6D6E7472u:
        v7 = CMValDisplay(hProfile);
        break;
      case 0x73636E72u:
        v7 = CMValInput(hProfile);
        break;
      case 0x61627374u:
        if ( (pHeader.phConnectionSpace == 1281450528 || pHeader.phConnectionSpace == 1482250784)
          && (pHeader.phDataColorSpace == 1482250784 || pHeader.phDataColorSpace == 1281450528) )
        {
          v7 = CMValAToB(hProfile);
          break;
        }
        break;
      case 0x6C696E6Bu:
        v7 = CMValLink(hProfile);
        break;
      case 0x6E6D636Cu:
        v7 = CMValNamed(hProfile);
        break;
      case 0x70727472u:
        v7 = CMValOutput(hProfile, &pHeader);
        break;
      case 0x73706163u:
        v7 = CMValColorSpace(hProfile);
        break;
      default:
        v7 = 0;
        break;
    }
    *a2 = v7;
  }
  return v4;
}

```

## disassembly

```asm
0x1800061dc  mov     [rsp-8+arg_10], rbx
0x1800061e1  push    rbp
0x1800061e2  push    rsi
0x1800061e3  push    rdi
0x1800061e4  lea     rbp, [rsp-47h]
0x1800061e9  sub     rsp, 0B0h
0x1800061f0  mov     rax, cs:__security_cookie
0x1800061f7  xor     rax, rsp
0x1800061fa  mov     [rbp+57h+var_20], rax
0x1800061fe  mov     rsi, rdx
0x180006201  mov     rbx, rcx
0x180006204  xor     edx, edx; Val
0x180006206  lea     rcx, [rbp+57h+pHeader]; void *
0x18000620a  mov     r8d, 80h; Size
0x180006210  call    memset_0
0x180006215  lea     rdx, [rbp+57h+pHeader]; pHeader
0x180006219  mov     byte ptr [rsi], 0
0x18000621c  mov     rcx, rbx; hProfile
0x18000621f  mov     edi, 7DBh
0x180006224  call    cs:__imp_GetColorProfileHeader
0x18000622a  cmp     [rbp+57h+pHeader.phSignature], 61637370h
0x180006231  jnz     short loc_180006237
0x180006233  test    eax, eax
0x180006235  jnz     short loc_180006258
0x180006237  mov     eax, edi
0x180006239  mov     rcx, [rbp+57h+var_20]
0x18000623d  xor     rcx, rsp; StackCookie
0x180006240  call    __security_check_cookie
0x180006245  mov     rbx, [rsp+0C0h+arg_10]
0x18000624d  add     rsp, 0B0h
0x180006254  pop     rdi
0x180006255  pop     rsi
0x180006256  pop     rbp
0x180006257  retn
0x180006258  mov     ecx, [rbp+57h+pHeader.phVersion]
0x18000625b  and     ecx, 0FF000000h
0x180006261  lea     eax, [rcx-2000000h]
0x180006267  cmp     eax, 2000000h
0x18000626c  ja      short loc_1800062C0
0x18000626e  cmp     ecx, 3000000h
0x180006274  jz      short loc_1800062C0
0x180006276  mov     eax, [rbp+57h+pHeader.phClass]
0x180006279  xor     edi, edi
0x18000627b  cmp     eax, 6D6E7472h
0x180006280  jnz     short loc_180006292
0x180006282  lea     rdx, [rbp+57h+pHeader]
0x180006286  mov     rcx, rbx; hProfile
0x180006289  call    CMValDisplay
0x18000628e  mov     [rsi], al
0x180006290  jmp     short loc_180006237
0x180006292  cmp     eax, 73636E72h
0x180006297  jz      short loc_1800062C8
0x180006299  cmp     eax, 61627374h
0x18000629e  jz      short loc_18000630E
0x1800062a0  cmp     eax, 6C696E6Bh
0x1800062a5  jz      short loc_180006300
0x1800062a7  cmp     eax, 6E6D636Ch
0x1800062ac  jz      short loc_1800062F2
0x1800062ae  cmp     eax, 70727472h
0x1800062b3  jz      short loc_1800062E4
0x1800062b5  cmp     eax, 73706163h
0x1800062ba  jz      short loc_1800062D6
0x1800062bc  xor     al, al
0x1800062be  jmp     short loc_18000628E
0x1800062c0  mov     byte ptr [rsi], 0
0x1800062c3  jmp     loc_180006237
0x1800062c8  lea     rdx, [rbp+57h+pHeader]
0x1800062cc  mov     rcx, rbx; hProfile
0x1800062cf  call    CMValInput
0x1800062d4  jmp     short loc_18000628E
0x1800062d6  lea     rdx, [rbp+57h+pHeader]
0x1800062da  mov     rcx, rbx; hProfile
0x1800062dd  call    CMValColorSpace
0x1800062e2  jmp     short loc_18000628E
0x1800062e4  lea     rdx, [rbp+57h+pHeader]
0x1800062e8  mov     rcx, rbx
0x1800062eb  call    CMValOutput
0x1800062f0  jmp     short loc_18000628E
0x1800062f2  lea     rdx, [rbp+57h+pHeader]
0x1800062f6  mov     rcx, rbx; hProfile
0x1800062f9  call    CMValNamed
0x1800062fe  jmp     short loc_18000628E
0x180006300  lea     rdx, [rbp+57h+pHeader]
0x180006304  mov     rcx, rbx; hProfile
0x180006307  call    CMValLink
0x18000630c  jmp     short loc_18000628E
0x18000630e  mov     ecx, 4C616220h
0x180006313  mov     eax, 58595A20h
0x180006318  cmp     [rbp+57h+pHeader.phConnectionSpace], ecx
0x18000631b  jz      short loc_180006322
0x18000631d  cmp     [rbp+57h+pHeader.phConnectionSpace], eax
0x180006320  jnz     short loc_1800062BC
0x180006322  cmp     [rbp+57h+pHeader.phDataColorSpace], eax
0x180006325  jz      short loc_18000632C
0x180006327  cmp     [rbp+57h+pHeader.phDataColorSpace], ecx
0x18000632a  jnz     short loc_1800062BC
0x18000632c  mov     rcx, rbx; hProfile
0x18000632f  call    CMValAToB
0x180006334  jmp     loc_18000628E
```
