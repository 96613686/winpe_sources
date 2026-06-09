# GetColorProfileElement

- ea: `0x18000cae0`
- end: `0x18000ccc3`
- name: `GetColorProfileElement`
- size: `483`
- prototype: `BOOL __stdcall(HPROFILE hProfile, TAGTYPE tag, DWORD dwOffset, PDWORD pcbElement, PVOID pElement, PBOOL pbReference)`
- caller_count: `7`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18000b864`
- `0x18000c3c0`
- `0x18000c924`
- `0x180029b68`
- `0x18003ef14`
- `0x180049360`
- `0x180049924`

## callees

- `0x18000cae0`
- `0x18000fe30`
- `0x1800127f0`
- `0x1800205f8`
- `0x18002e5f0`
- `0x18002f2dc`

## import_xrefs

- `ntdll!RtlLogUnexpectedCodepath` at `0x18000cbf7`
- `ntdll!RtlLogUnexpectedCodepath` at `0x18000cbf7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cc11`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cc7f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cc96`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cc11`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cc7f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cc96`

## pseudocode

```c
BOOL __stdcall GetColorProfileElement(
        HPROFILE hProfile,
        TAGTYPE tag,
        DWORD dwOffset,
        PDWORD pcbElement,
        PVOID pElement,
        PBOOL pbReference)
{
  unsigned __int64 v6; // rdi
  DWORD v9; // ecx
  void *v10; // r10
  BOOL v11; // r15d
  __int64 v12; // rbx
  DWORD v13; // eax
  unsigned __int32 v14; // esi
  unsigned __int64 v15; // r12
  unsigned int v16; // ebp
  DWORD v17; // r8d
  unsigned __int64 v18; // rax
  DWORD v19; // r8d
  DWORD v20; // esi
  DWORD pnElementCount; // [rsp+20h] [rbp-68h] BYREF
  DWORD v23; // [rsp+24h] [rbp-64h]
  void *v24; // [rsp+28h] [rbp-60h]
  __int64 v25; // [rsp+30h] [rbp-58h] BYREF
  int v26; // [rsp+38h] [rbp-50h]

  v6 = (unsigned __int64)hProfile ^ 0x49434D20;
  v23 = dwOffset;
  v24 = pElement;
  pnElementCount = 0;
  if ( !hProfile || !v6 || *(_DWORD *)v6 != 1129860428 )
  {
    if ( (unsigned int)ValidHandle(hProfile, 1347569228) && pcbElement && pbReference )
    {
      if ( !GetCountColorProfileElements(v10, &pnElementCount) )
        goto LABEL_27;
      v11 = 0;
      v12 = *(_QWORD *)(v6 + 56) + 132LL;
      v13 = 0;
      v14 = _byteswap_ulong(tag);
      while ( 1 )
      {
        if ( v13 >= pnElementCount )
        {
          SetLastError(0x7DCu);
          return v11;
        }
        if ( *(_DWORD *)v12 == v14 )
          break;
        v12 += 12;
        ++v13;
      }
      v15 = *(unsigned int *)(v6 + 48);
      v16 = _byteswap_ulong(*(_DWORD *)(v12 + 4));
      v17 = _byteswap_ulong(*(_DWORD *)(v12 + 8));
      if ( v16 >= (unsigned int)v15 || v17 < 8 )
      {
LABEL_27:
        v9 = 2011;
        goto LABEL_29;
      }
      if ( v17 > (unsigned int)v15 - v16 )
      {
        v25 = 49538476;
        v26 = 87;
        RtlLogUnexpectedCodepath(&v25);
        v17 = v15 - v16;
      }
      if ( !v24 )
      {
        *pcbElement = v17;
        SetLastError(0x7Au);
        goto LABEL_24;
      }
      if ( v23 < v17 )
      {
        v18 = v17;
        v19 = v17 - v23;
        if ( v23 + (unsigned __int64)*pcbElement <= v18 )
          v19 = *pcbElement;
        v20 = v19;
        if ( v23 + v19 + (unsigned __int64)v16 <= v15 )
        {
          memcpy_0(v24, (const void *)(v23 + *(_QWORD *)(v6 + 56) + _byteswap_ulong(*(_DWORD *)(v12 + 4))), v19);
          *pcbElement = v20;
          v11 = 1;
LABEL_24:
          *pbReference = IsReferenceTag((struct tagPROFOBJ *)v6, (struct tagTAGDATA *)v12);
          return v11;
        }
      }
    }
    v9 = 87;
    goto LABEL_29;
  }
  v9 = 50;
LABEL_29:
  SetLastError(v9);
  return 0;
}

```

## disassembly

```asm
0x18000cae0  mov     [rsp+arg_8], rbx
0x18000cae5  push    rbp
0x18000cae6  push    rsi
0x18000cae7  push    rdi
0x18000cae8  push    r12
0x18000caea  push    r13
0x18000caec  push    r14
0x18000caee  push    r15
0x18000caf0  sub     rsp, 50h
0x18000caf4  mov     rax, cs:__security_cookie
0x18000cafb  xor     rax, rsp
0x18000cafe  mov     [rsp+88h+var_48], rax
0x18000cb03  mov     rax, [rsp+88h+pElement]
0x18000cb0b  mov     rdi, rcx
0x18000cb0e  mov     r13, [rsp+88h+pbReference]
0x18000cb16  xor     rdi, 49434D20h
0x18000cb1d  mov     [rsp+88h+var_64], r8d
0x18000cb22  mov     r14, r9
0x18000cb25  mov     [rsp+88h+var_60], rax
0x18000cb2a  mov     esi, edx
0x18000cb2c  mov     [rsp+88h+pnElementCount], 0
0x18000cb34  mov     r10, rcx
0x18000cb37  test    rcx, rcx
0x18000cb3a  jz      short loc_18000CB53
0x18000cb3c  test    rdi, rdi
0x18000cb3f  jz      short loc_18000CB53
0x18000cb41  cmp     dword ptr [rdi], 43584D4Ch
0x18000cb47  jnz     short loc_18000CB53
0x18000cb49  mov     ecx, 32h ; '2'
0x18000cb4e  jmp     loc_18000CC96
0x18000cb53  mov     edx, 5052464Ch
0x18000cb58  call    ValidHandle
0x18000cb5d  test    eax, eax
0x18000cb5f  jz      loc_18000CC91
0x18000cb65  test    r14, r14
0x18000cb68  jz      loc_18000CC91
0x18000cb6e  test    r13, r13
0x18000cb71  jz      loc_18000CC91
0x18000cb77  lea     rdx, [rsp+88h+pnElementCount]; pnElementCount
0x18000cb7c  mov     rcx, r10; hProfile
0x18000cb7f  call    GetCountColorProfileElements
0x18000cb84  test    eax, eax
0x18000cb86  jz      loc_18000CC8A
0x18000cb8c  mov     rbx, [rdi+38h]
0x18000cb90  xor     r15d, r15d
0x18000cb93  add     rbx, 84h
0x18000cb9a  xor     eax, eax
0x18000cb9c  bswap   esi
0x18000cb9e  cmp     eax, [rsp+88h+pnElementCount]
0x18000cba2  jnb     loc_18000CC7A
0x18000cba8  cmp     [rbx], esi
0x18000cbaa  jz      short loc_18000CBB4
0x18000cbac  add     rbx, 0Ch
0x18000cbb0  inc     eax
0x18000cbb2  jmp     short loc_18000CB9E
0x18000cbb4  mov     ebp, [rbx+4]
0x18000cbb7  mov     r12d, [rdi+30h]
0x18000cbbb  mov     r8d, [rbx+8]
0x18000cbbf  bswap   ebp
0x18000cbc1  bswap   r8d
0x18000cbc4  cmp     ebp, r12d
0x18000cbc7  jnb     loc_18000CC8A
0x18000cbcd  cmp     r8d, 8
0x18000cbd1  jb      loc_18000CC8A
0x18000cbd7  mov     esi, r12d
0x18000cbda  sub     esi, ebp
0x18000cbdc  cmp     r8d, esi
0x18000cbdf  jbe     short loc_18000CC00
0x18000cbe1  lea     rcx, [rsp+88h+var_58]
0x18000cbe6  mov     [rsp+88h+var_58], 2F3E5ACh
0x18000cbef  mov     [rsp+88h+var_50], 57h ; 'W'
0x18000cbf7  call    cs:__imp_RtlLogUnexpectedCodepath
0x18000cbfd  mov     r8d, esi
0x18000cc00  mov     r11, [rsp+88h+var_60]
0x18000cc05  test    r11, r11
0x18000cc08  jnz     short loc_18000CC19
0x18000cc0a  lea     ecx, [r11+7Ah]; dwErrCode
0x18000cc0e  mov     [r14], r8d
0x18000cc11  call    cs:__imp_SetLastError
0x18000cc17  jmp     short loc_18000CC69
0x18000cc19  mov     r10d, [rsp+88h+var_64]
0x18000cc1e  cmp     r10d, r8d
0x18000cc21  jnb     short loc_18000CC91
0x18000cc23  mov     edx, [r14]
0x18000cc26  mov     eax, r8d
0x18000cc29  sub     r8d, r10d
0x18000cc2c  lea     rcx, [r10+rdx]
0x18000cc30  cmp     rcx, rax
0x18000cc33  cmovbe  r8d, edx
0x18000cc37  mov     edx, ebp
0x18000cc39  mov     esi, r8d
0x18000cc3c  add     rdx, rsi
0x18000cc3f  add     rdx, r10
0x18000cc42  cmp     rdx, r12
0x18000cc45  ja      short loc_18000CC91
0x18000cc47  mov     edx, [rbx+4]
0x18000cc4a  mov     r8d, esi; Size
0x18000cc4d  bswap   edx
0x18000cc4f  mov     edx, edx
0x18000cc51  mov     rcx, r11; void *
0x18000cc54  add     rdx, [rdi+38h]
0x18000cc58  add     rdx, r10; Src
0x18000cc5b  call    memcpy_0
0x18000cc60  mov     [r14], esi
0x18000cc63  mov     r15d, 1
0x18000cc69  mov     rdx, rbx; struct tagTAGDATA *
0x18000cc6c  mov     rcx, rdi; struct tagPROFOBJ *
0x18000cc6f  call    ?IsReferenceTag@@YAHPEAUtagPROFOBJ@@PEAUtagTAGDATA@@@Z; IsReferenceTag(tagPROFOBJ *,tagTAGDATA *)
0x18000cc74  mov     [r13+0], eax
0x18000cc78  jmp     short loc_18000CC85
0x18000cc7a  mov     ecx, 7DCh; dwErrCode
0x18000cc7f  call    cs:__imp_SetLastError
0x18000cc85  mov     eax, r15d
0x18000cc88  jmp     short loc_18000CC9E
0x18000cc8a  mov     ecx, 7DBh
0x18000cc8f  jmp     short loc_18000CC96
0x18000cc91  mov     ecx, 57h ; 'W'; dwErrCode
0x18000cc96  call    cs:__imp_SetLastError
0x18000cc9c  xor     eax, eax
0x18000cc9e  mov     rcx, [rsp+88h+var_48]
0x18000cca3  xor     rcx, rsp; StackCookie
0x18000cca6  call    __security_check_cookie
0x18000ccab  mov     rbx, [rsp+88h+arg_8]
0x18000ccb3  add     rsp, 50h
0x18000ccb7  pop     r15
0x18000ccb9  pop     r14
0x18000ccbb  pop     r13
0x18000ccbd  pop     r12
0x18000ccbf  pop     rdi
0x18000ccc0  pop     rsi
0x18000ccc1  pop     rbp
0x18000ccc2  retn
```
