# BiOpenSystemStore

- ea: `0x14098b954`
- end: `0x14098bbf7`
- name: `BiOpenSystemStore`
- size: `675`
- prototype: ``
- caller_count: `2`
- callee_count: `18`
- tags: `registry_config`

## callers

- `0x14072b778`
- `0x140732aa8`

## callees

- `0x14053d080`
- `0x14053f320`
- `0x1406daa70`
- `0x140987284`
- `0x1409875c8`
- `0x1409876cc`
- `0x140989b74`
- `0x14098ad6c`
- `0x14098aea4`
- `0x14098b1b8`
- `0x14098b954`
- `0x14098bcb8`
- `0x14098be90`
- `0x14098bea4`
- `0x14098d68c`
- `0x14098dc20`
- `0x140ae4a14`
- `0x140bae8e0`

## string_xrefs

- `0x14098b9b7`: `\Registry\Machine`
- `0x14098b988`: `Opening system store. Flags: 0x%x`
- `0x14098bafa`: `The system store is not already loaded`
- `0x14098bbae`: `Specified flags prevent opening unloaded system store`

## pseudocode

```c
__int64 __fastcall BiOpenSystemStore(unsigned __int64 *a1, unsigned int a2)
{
  unsigned __int64 v2; // rdi
  char v4; // r8
  int v5; // ebx
  int v7; // eax
  _QWORD *v8; // r14
  __int64 i; // rsi
  bool v10; // zf
  int v11; // r15d
  __int64 v12; // rsi
  int v13; // eax
  __int64 v14; // r8
  __int64 v15; // r9
  int v16; // eax
  int v17; // eax
  int v18; // eax
  HANDLE Handle[2]; // [rsp+20h] [rbp-10h] BYREF
  unsigned int v21; // [rsp+78h] [rbp+48h] BYREF
  PVOID P; // [rsp+80h] [rbp+50h] BYREF
  HANDLE v23; // [rsp+88h] [rbp+58h] BYREF

  v2 = 0;
  *a1 = 0;
  v21 = 0;
  Handle[0] = 0;
  v23 = 0;
  P = 0;
  BiLogMessage(2, L"Opening system store. Flags: 0x%x", a2);
  BiCleanupLoadedStores(16 * (v4 & 1u));
  v5 = BiOpenKeyNonBcd(0, L"\\Registry\\Machine", 983103, Handle);
  if ( v5 < 0 )
    goto LABEL_2;
  v7 = BiEnumerateSubKeys(Handle[0], &P, &v21);
  v8 = P;
  v5 = v7;
  if ( v7 >= 0 )
  {
    LODWORD(P) = 0;
    v5 = -1073741275;
    for ( i = 0; ; i = (unsigned int)(i + 1) )
    {
      v10 = (_DWORD)i == v21;
      if ( (unsigned int)i >= v21 )
        break;
      if ( !wcsnicmp((const wchar_t *)v8[i], L"BCD", 3u) && wcstoul((const wchar_t *)(v8[i] + 6LL), 0, 10) != -1 )
      {
        BiLogMessage(2, L"Found loaded store at key %s", v8[i]);
        v18 = BiOpenKey(Handle[0], v8[i], 131097, &v23);
        v2 = (unsigned __int64)v23;
        v5 = v18;
        if ( v18 >= 0 )
        {
          if ( (unsigned __int8)BiIsSystemStore(v23) )
          {
            BiLogMessage(2, L"Store %s is the system store", v8[i]);
            v5 = 0;
            v10 = (_DWORD)i == v21;
            break;
          }
          BiCloseKey((HANDLE)v2);
        }
      }
    }
    if ( v10 )
    {
      BiLogMessage(2, L"The system store is not already loaded");
      v23 = 0;
      if ( (a2 & 4) != 0 )
      {
        BiLogMessage(4, L"Specified flags prevent opening unloaded system store");
        v5 = -1073741275;
        goto LABEL_20;
      }
      v17 = BiLoadSystemStore(&v23);
      v2 = (unsigned __int64)v23;
      v5 = v17;
      if ( v17 < 0 )
      {
        v11 = (int)P;
        goto LABEL_18;
      }
      v11 = 1;
    }
    else
    {
      v11 = (int)P;
    }
    if ( (a2 & 2) != 0 )
    {
      v2 |= 2u;
      goto LABEL_29;
    }
    v12 = (unsigned __int8)BiWasFirmwareModified(v2);
    BiLogMessage(2, L"Synchronizing store with firmware. FirmwareModified: %d", v12);
    v13 = BiGetFirmwareType(0) - 1;
    if ( v13 )
    {
      v16 = v13 - 1;
      if ( !v16 )
      {
        v5 = BiBindEfiNamespaceObjects(v2);
        v15 = (unsigned int)v5;
        if ( v5 < 0 )
        {
LABEL_17:
          BiLogMessage(4, L"Failed to bind with firmware. Flags: 0x%x Status: %x", a2, v15);
          goto LABEL_18;
        }
        goto LABEL_36;
      }
      if ( v16 != 1 )
      {
        v5 = -1073741637;
        v15 = 3221225659LL;
        goto LABEL_17;
      }
    }
    v5 = 0;
LABEL_36:
    if ( !(_BYTE)v12 )
      BiSetFirmwareModified(v2, 0, v14, v15);
LABEL_29:
    *a1 = v2;
    if ( v5 >= 0 )
      goto LABEL_20;
LABEL_18:
    if ( v2 )
      BiCloseStore(v2, v11 != 0 ? 2 : 0);
  }
LABEL_20:
  if ( v8 )
    ExFreePoolWithTag(v8, 0x4B444342u);
LABEL_2:
  if ( Handle[0] )
    ZwClose(Handle[0]);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x14098b954  mov     [rsp-38h+arg_0], rcx
0x14098b959  push    rbp
0x14098b95a  push    rbx
0x14098b95b  push    rsi
0x14098b95c  push    rdi
0x14098b95d  push    r13
0x14098b95f  push    r14
0x14098b961  push    r15
0x14098b963  mov     rbp, rsp
0x14098b966  sub     rsp, 30h
0x14098b96a  xor     edi, edi
0x14098b96c  mov     qword ptr [rcx], 0
0x14098b973  mov     r8d, edx
0x14098b976  mov     [rbp+arg_8], 0
0x14098b97d  mov     r13d, edx
0x14098b980  mov     [rbp+Handle], 0
0x14098b988  lea     rdx, aOpeningSystemS; "Opening system store. Flags: 0x%x"
0x14098b98f  mov     [rbp+arg_18], rdi
0x14098b993  lea     ecx, [rdi+2]
0x14098b996  mov     [rbp+P], rdi
0x14098b99a  call    BiLogMessage
0x14098b99f  mov     ecx, r8d
0x14098b9a2  and     ecx, 1
0x14098b9a5  shl     ecx, 4
0x14098b9a8  call    BiCleanupLoadedStores
0x14098b9ad  lea     r9, [rbp+Handle]
0x14098b9b1  mov     r8d, 0F003Fh
0x14098b9b7  lea     rdx, aRegistryMachin_231; "\\Registry\\Machine"
0x14098b9be  xor     ecx, ecx
0x14098b9c0  call    BiOpenKeyNonBcd
0x14098b9c5  mov     ebx, eax
0x14098b9c7  test    eax, eax
0x14098b9c9  jns     short loc_14098B9ED
0x14098b9cb  cmp     [rbp+Handle], 0
0x14098b9d0  jz      short loc_14098B9DB
0x14098b9d2  mov     rcx, [rbp+Handle]; Handle
0x14098b9d6  call    ZwClose
0x14098b9db  mov     eax, ebx
0x14098b9dd  add     rsp, 30h
0x14098b9e1  pop     r15
0x14098b9e3  pop     r14
0x14098b9e5  pop     r13
0x14098b9e7  pop     rdi
0x14098b9e8  pop     rsi
0x14098b9e9  pop     rbx
0x14098b9ea  pop     rbp
0x14098b9eb  retn
0x14098b9ed  mov     rcx, [rbp+Handle]
0x14098b9f1  lea     r8, [rbp+arg_8]
0x14098b9f5  lea     rdx, [rbp+P]
0x14098b9f9  call    BiEnumerateSubKeys
0x14098b9fe  mov     r14, [rbp+P]
0x14098ba02  mov     ebx, eax
0x14098ba04  test    eax, eax
0x14098ba06  js      loc_14098BADF
0x14098ba0c  mov     dword ptr [rbp+P], edi
0x14098ba0f  mov     ebx, 0C0000225h
0x14098ba14  xor     esi, esi
0x14098ba16  cmp     esi, [rbp+arg_8]
0x14098ba19  jnb     short loc_14098BA55
0x14098ba1b  mov     rcx, [r14+rsi*8]; Str1
0x14098ba1f  lea     rdx, aBcd; "BCD"
0x14098ba26  mov     r8d, 3; MaxCount
0x14098ba2c  call    _wcsnicmp
0x14098ba31  test    eax, eax
0x14098ba33  jnz     short loc_14098BA51
0x14098ba35  mov     rcx, [r14+rsi*8]
0x14098ba39  lea     r8d, [rax+0Ah]; Radix
0x14098ba3d  add     rcx, 6; Str
0x14098ba41  xor     edx, edx; EndPtr
0x14098ba43  call    wcstoul
0x14098ba48  cmp     eax, 0FFFFFFFFh
0x14098ba4b  jnz     loc_14098BB3F
0x14098ba51  inc     esi
0x14098ba53  jmp     short loc_14098BA16
0x14098ba55  jz      loc_14098BAFA
0x14098ba5b  mov     r15d, dword ptr [rbp+P]
0x14098ba5f  test    r13b, 2
0x14098ba63  jnz     loc_14098BB96
0x14098ba69  mov     rcx, rdi
0x14098ba6c  call    BiWasFirmwareModified
0x14098ba71  movzx   esi, al
0x14098ba74  lea     rdx, aSynchronizingS; "Synchronizing store with firmware. Firm"...
0x14098ba7b  mov     r8d, esi
0x14098ba7e  mov     ecx, 2
0x14098ba83  call    BiLogMessage
0x14098ba88  xor     ecx, ecx
0x14098ba8a  call    BiGetFirmwareType
0x14098ba8f  sub     eax, 1
0x14098ba92  jz      loc_14098BBE4
0x14098ba98  sub     eax, 1
0x14098ba9b  jnz     loc_14098BBD2
0x14098baa1  mov     rcx, rdi
0x14098baa4  call    BiBindEfiNamespaceObjects
0x14098baa9  mov     ebx, eax
0x14098baab  mov     r9d, eax
0x14098baae  test    eax, eax
0x14098bab0  jns     loc_14098BBE6
0x14098bab6  mov     r8d, r13d
0x14098bab9  lea     rdx, aFailedToBindWi; "Failed to bind with firmware. Flags: 0x"...
0x14098bac0  mov     ecx, 4
0x14098bac5  call    BiLogMessage
0x14098baca  test    rdi, rdi
0x14098bacd  jz      short loc_14098BADF
0x14098bacf  neg     r15d
0x14098bad2  mov     rcx, rdi
0x14098bad5  sbb     edx, edx
0x14098bad7  and     edx, 2
0x14098bada  call    BiCloseStore
0x14098badf  test    r14, r14
0x14098bae2  jz      loc_14098B9CB
0x14098bae8  mov     edx, 4B444342h; Tag
0x14098baed  mov     rcx, r14; P
0x14098baf0  call    ExFreePoolWithTag
0x14098baf5  jmp     loc_14098B9CB
0x14098bafa  lea     rdx, aTheSystemStore; "The system store is not already loaded"
0x14098bb01  mov     ecx, 2
0x14098bb06  call    BiLogMessage
0x14098bb0b  mov     [rbp+arg_18], 0
0x14098bb13  test    r13b, 4
0x14098bb17  jnz     loc_14098BBAE
0x14098bb1d  lea     rcx, [rbp+arg_18]
0x14098bb21  call    BiLoadSystemStore
0x14098bb26  mov     rdi, [rbp+arg_18]
0x14098bb2a  mov     ebx, eax
0x14098bb2c  test    eax, eax
0x14098bb2e  js      loc_14098BBC9
0x14098bb34  mov     r15d, 1
0x14098bb3a  jmp     loc_14098BA5F
0x14098bb3f  mov     r8, [r14+rsi*8]
0x14098bb43  lea     rdx, aFoundLoadedSto; "Found loaded store at key %s"
0x14098bb4a  mov     ecx, 2
0x14098bb4f  call    BiLogMessage
0x14098bb54  mov     rdx, [r14+rsi*8]
0x14098bb58  lea     r9, [rbp+arg_18]
0x14098bb5c  mov     rcx, [rbp+Handle]
0x14098bb60  mov     r8d, 20019h
0x14098bb66  call    BiOpenKey
0x14098bb6b  mov     rdi, [rbp+arg_18]
0x14098bb6f  mov     ebx, eax
0x14098bb71  test    eax, eax
0x14098bb73  js      loc_14098BA51
0x14098bb79  mov     rcx, rdi
0x14098bb7c  call    BiIsSystemStore
0x14098bb81  test    al, al
0x14098bb83  jnz     loc_140B61BE0
0x14098bb89  mov     rcx, rdi; Handle
0x14098bb8c  call    BiCloseKey
0x14098bb91  jmp     loc_14098BA51
0x14098bb96  or      rdi, 2
0x14098bb9a  mov     rax, [rbp+arg_0]
0x14098bb9e  mov     [rax], rdi
0x14098bba1  test    ebx, ebx
0x14098bba3  js      loc_14098BACA
0x14098bba9  jmp     loc_14098BADF
0x14098bbae  lea     rdx, aSpecifiedFlags; "Specified flags prevent opening unloade"...
0x14098bbb5  mov     ecx, 4
0x14098bbba  call    BiLogMessage
0x14098bbbf  mov     ebx, 0C0000225h
0x14098bbc4  jmp     loc_14098BADF
0x14098bbc9  mov     r15d, dword ptr [rbp+P]
0x14098bbcd  jmp     loc_14098BACA
0x14098bbd2  cmp     eax, 1
0x14098bbd5  jz      short loc_14098BBE4
0x14098bbd7  mov     ebx, 0C00000BBh
0x14098bbdc  mov     r9d, ebx
0x14098bbdf  jmp     loc_14098BAB6
0x14098bbe4  xor     ebx, ebx
0x14098bbe6  test    sil, sil
0x14098bbe9  jnz     short loc_14098BB9A
0x14098bbeb  xor     edx, edx
0x14098bbed  mov     rcx, rdi
0x14098bbf0  call    BiSetFirmwareModified
0x14098bbf5  jmp     short loc_14098BB9A
0x140b61be0  mov     r8, [r14+rsi*8]
0x140b61be4  lea     rdx, aStoreSIsTheSys; "Store %s is the system store"
0x140b61beb  mov     ecx, 2
0x140b61bf0  call    BiLogMessage
0x140b61bf5  xor     ebx, ebx
0x140b61bf7  cmp     esi, [rbp+arg_8]
0x140b61bfa  jmp     loc_14098BA55
```
