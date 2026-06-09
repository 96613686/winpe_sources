# SdbOpenDatabaseEx

- ea: `0x180020904`
- end: `0x180020c72`
- name: `SdbOpenDatabaseEx`
- size: `878`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800201a0`
- `0x18007ce9c`

## callees

- `0x18001ef8c`
- `0x18001f00c`
- `0x18001f138`
- `0x18001f74c`
- `0x180020904`
- `0x180020c78`
- `0x180021f74`
- `0x180022314`
- `0x180045c34`
- `0x18004fdf0`
- `0x180079504`
- `0x180081634`
- `0x18008275d`
- `0x1800827c0`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18002098f`
- `ntdll!RtlAllocateHeap` at `0x18002098f`

## string_xrefs

- `0x18002092e`: `Flags:%d; DatabasePath:%ws`
- `0x180020aa0`: `SdbGetMergeRedirectPath failed to check for sdb merge redirect [%x]`
- `0x180020949`: `SdbOpenDatabaseEx`
- `0x1800209b4`: `SdbOpenDatabaseEx`
- `0x180020a49`: `SdbOpenDatabaseEx`
- `0x180020a86`: `SdbOpenDatabaseEx`
- `0x180020ab2`: `SdbOpenDatabaseEx`
- `0x180020b09`: `SdbOpenDatabaseEx`
- `0x180020bdb`: `SdbOpenDatabaseEx`
- `0x180020c1a`: `SdbOpenDatabaseEx`
- `0x180020c0d`: `Failed to open SDB - File size too large or small.`
- `0x180020a75`: `Failed to create file mapping for redirected SDB file [%x]`
- `0x180020afc`: `Failed to create file mapping [%x]`
- `0x180020bce`: `SdbpOpenCompressedDatabase failed to open compressed database.`
- `0x180020b7d`: `Failed to read database header`

## pseudocode

```c
_QWORD *__fastcall SdbOpenDatabaseEx(const WCHAR *a1, __int64 a2, unsigned int a3)
{
  const WCHAR *v5; // rax
  _QWORD *Heap; // rax
  _QWORD *v7; // rbx
  int MergeRedirectPath; // r14d
  int v9; // esi
  const char *v10; // r9
  int v11; // r8d
  __int64 v12; // rsi
  __int64 v13; // rdx
  const WCHAR *v16; // [rsp+28h] [rbp-38h]
  int v17; // [rsp+30h] [rbp-30h] BYREF
  __int64 v18; // [rsp+38h] [rbp-28h] BYREF
  _QWORD *v19; // [rsp+40h] [rbp-20h] BYREF
  __int64 v20; // [rsp+48h] [rbp-18h] BYREF
  int v21; // [rsp+50h] [rbp-10h]

  v20 = 0;
  v21 = 0;
  v17 = 0;
  v5 = a1;
  if ( !a1 )
    v5 = &word_18008EBAC;
  v16 = v5;
  AslLogCallPrintf(3, (unsigned int)"SdbOpenDatabaseEx", 2499, (unsigned int)"Flags:%d; DatabasePath:%ws");
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0xA80u);
  v19 = Heap;
  v7 = Heap;
  if ( Heap )
  {
    memset_0(Heap, 0, 0xA80u);
    v18 = 0;
    if ( (a3 & 0x10) != 0 )
      goto LABEL_23;
    MergeRedirectPath = SdbGetMergeRedirectPath(&v18, &v17, (a3 & 0x20) == 0, a1, a3, v16);
    if ( MergeRedirectPath < 0 )
    {
      if ( MergeRedirectPath != -1073741772 )
        AslLogCallPrintf(
          3,
          (unsigned int)"SdbOpenDatabaseEx",
          2525,
          (unsigned int)"SdbGetMergeRedirectPath failed to check for sdb merge redirect [%x]");
      v9 = MergeRedirectPath;
    }
    else if ( v18 )
    {
      if ( (a3 & 0x20) != 0 )
      {
        if ( !v17 )
          *((_DWORD *)v7 + 6) |= 0x20u;
      }
      else if ( v17 )
      {
        AslPathGetFileNamePart(a1);
        AslLogCallPrintf(
          1,
          (unsigned int)"SdbOpenDatabaseEx",
          2537,
          (unsigned int)"Handled Error: MergeSdb staged deletion feature was used to prevent sdb mismatch error. SdbName: [%ls].");
      }
      v9 = AslFileMappingCreate(v7, v18);
      if ( v9 < 0 )
        AslLogCallPrintf(
          1,
          (unsigned int)"SdbOpenDatabaseEx",
          2556,
          (unsigned int)"Failed to create file mapping for redirected SDB file [%x]");
    }
    else
    {
      v9 = -1073741772;
    }
    if ( v18 )
      AslFree(NtCurrentPeb()->ProcessHeap, v18);
    if ( v9 < 0 || !*v7 )
    {
LABEL_23:
      if ( (int)AslFileMappingCreate(v7, a1) < 0 )
      {
        v10 = "Failed to create file mapping [%x]";
        v11 = 2578;
LABEL_41:
        AslLogCallPrintf(1, (unsigned int)"SdbOpenDatabaseEx", v11, (_DWORD)v10);
LABEL_42:
        if ( v7 )
        {
          AslFileMappingDelete(*v7);
          AslFree(NtCurrentPeb()->ProcessHeap, v7);
        }
        return 0;
      }
    }
    v12 = *(_QWORD *)(*v7 + 24LL);
    if ( (unsigned __int64)(v12 - 42) > 0xFFFFFD5 )
    {
      v10 = "Failed to open SDB - File size too large or small.";
      v11 = 2587;
      goto LABEL_41;
    }
    if ( (int)AslFileMappingEnsureMappedAsEx() < 0 )
    {
      v10 = "Failed to map SDB [%x]";
      v11 = 2593;
      goto LABEL_41;
    }
    *((_DWORD *)v7 + 4) = 0;
    *((_DWORD *)v7 + 5) = v12;
    v7[1] = AslFileMappingGetViewBase(*v7);
    if ( !(unsigned int)SdbpReadMappedData(v7, 0, &v20, 12) )
    {
      v10 = "Failed to read database header";
      v11 = 2606;
      goto LABEL_41;
    }
    if ( v21 != 1717724275 )
    {
      if ( v21 == 1717724282 )
      {
        if ( !(unsigned int)SdbpOpenCompressedDatabase(&v19, v13, a3) )
        {
          AslLogCallPrintf(
            1,
            (unsigned int)"SdbOpenDatabaseEx",
            2625,
            (unsigned int)"SdbpOpenCompressedDatabase failed to open compressed database.");
          v7 = v19;
          goto LABEL_42;
        }
        return v19;
      }
      if ( (a3 & 2) == 0 )
      {
        v10 = "Magic does not match a valid value: 0x%lx";
        v11 = 2619;
        goto LABEL_41;
      }
    }
    if ( !(unsigned int)SdbpValidateAndApplyCompatFlags(v7, &v20, a3) )
      goto LABEL_42;
    return v7;
  }
  AslLogCallPrintf(1, (unsigned int)"SdbOpenDatabaseEx", 2507, (unsigned int)"Failed to allocate DB structure");
  return 0;
}

```

## disassembly

```asm
0x180020904  mov     r11, rsp
0x180020907  mov     [r11+10h], rbx
0x18002090b  mov     [r11+20h], rsi
0x18002090f  push    rbp
0x180020910  push    rdi
0x180020911  push    r12
0x180020913  push    r13
0x180020915  push    r14
0x180020917  mov     rbp, rsp
0x18002091a  sub     rsp, 60h
0x18002091e  mov     rax, cs:__security_cookie
0x180020925  xor     rax, rsp
0x180020928  mov     [rbp+var_8], rax
0x18002092c  xor     eax, eax
0x18002092e  lea     r9, aFlagsDDatabase; "Flags:%d; DatabasePath:%ws"
0x180020935  mov     r13, rcx
0x180020938  mov     [rbp+var_18], rax
0x18002093c  mov     [rbp+var_10], eax
0x18002093f  lea     rcx, word_18008EBAC
0x180020946  mov     [rbp+var_30], eax
0x180020949  lea     rdx, aSdbopendatabas; "SdbOpenDatabaseEx"
0x180020950  mov     r12d, r8d
0x180020953  test    r13, r13
0x180020956  mov     rax, r13
0x180020959  cmovz   rax, rcx
0x18002095d  mov     ecx, 3
0x180020962  mov     [r11-60h], rax
0x180020966  mov     [r11-68h], r8d
0x18002096a  mov     r8d, 9C3h
0x180020970  call    AslLogCallPrintf
0x180020975  mov     rcx, gs:60h
0x18002097e  mov     edi, 0A80h
0x180020983  mov     r8d, edi; Size
0x180020986  mov     edx, 8; Flags
0x18002098b  mov     rcx, [rcx+30h]; HeapHandle
0x18002098f  call    cs:__imp_RtlAllocateHeap
0x180020996  nop     dword ptr [rax+rax+00h]
0x18002099b  mov     [rbp+var_20], rax
0x18002099f  mov     rbx, rax
0x1800209a2  test    rax, rax
0x1800209a5  jnz     short loc_1800209C8
0x1800209a7  lea     r9, aFailedToAlloca_10; "Failed to allocate DB structure"
0x1800209ae  mov     r8d, 9CBh
0x1800209b4  lea     rdx, aSdbopendatabas; "SdbOpenDatabaseEx"
0x1800209bb  lea     ecx, [rax+1]
0x1800209be  call    AslLogCallPrintf
0x1800209c3  jmp     loc_180020C4A
0x1800209c8  mov     r8, rdi; Size
0x1800209cb  xor     edx, edx; Val
0x1800209cd  mov     rcx, rbx; void *
0x1800209d0  call    memset_0
0x1800209d5  mov     [rbp+var_28], 0
0x1800209dd  mov     edi, 1
0x1800209e2  test    r12b, 10h
0x1800209e6  jnz     loc_180020AED
0x1800209ec  lea     r8d, [rdi-1]
0x1800209f0  mov     esi, r12d
0x1800209f3  and     esi, 20h
0x1800209f6  lea     rdx, [rbp+var_30]
0x1800209fa  mov     r9, r13
0x1800209fd  lea     rcx, [rbp+var_28]
0x180020a01  setz    r8b
0x180020a05  call    SdbGetMergeRedirectPath
0x180020a0a  mov     r14d, eax
0x180020a0d  test    eax, eax
0x180020a0f  js      loc_180020A96
0x180020a15  cmp     [rbp+var_28], 0
0x180020a1a  jnz     short loc_180020A26
0x180020a1c  mov     esi, 0C0000034h
0x180020a21  jmp     loc_180020AC6
0x180020a26  test    esi, esi
0x180020a28  jnz     short loc_180020A59
0x180020a2a  cmp     [rbp+var_30], esi
0x180020a2d  jz      short loc_180020A63
0x180020a2f  mov     rcx, r13
0x180020a32  call    AslPathGetFileNamePart
0x180020a37  lea     r9, aHandledErrorMe; "Handled Error: MergeSdb staged deletion"...
0x180020a3e  mov     [rsp+60h+var_40], rax
0x180020a43  mov     r8d, 9E9h
0x180020a49  lea     rdx, aSdbopendatabas; "SdbOpenDatabaseEx"
0x180020a50  mov     ecx, edi
0x180020a52  call    AslLogCallPrintf
0x180020a57  jmp     short loc_180020A63
0x180020a59  cmp     [rbp+var_30], 0
0x180020a5d  jnz     short loc_180020A63
0x180020a5f  or      dword ptr [rbx+18h], 20h
0x180020a63  mov     rdx, [rbp+var_28]
0x180020a67  mov     rcx, rbx
0x180020a6a  call    AslFileMappingCreate
0x180020a6f  mov     esi, eax
0x180020a71  test    eax, eax
0x180020a73  jns     short loc_180020AC6
0x180020a75  lea     r9, aFailedToCreate_0; "Failed to create file mapping for redir"...
0x180020a7c  mov     dword ptr [rsp+60h+var_40], eax
0x180020a80  mov     r8d, 9FCh
0x180020a86  lea     rdx, aSdbopendatabas; "SdbOpenDatabaseEx"
0x180020a8d  mov     ecx, edi
0x180020a8f  call    AslLogCallPrintf
0x180020a94  jmp     short loc_180020AC6
0x180020a96  mov     esi, 0C0000034h
0x180020a9b  cmp     r14d, esi
0x180020a9e  jz      short loc_180020AC3
0x180020aa0  lea     r9, aSdbgetmergered; "SdbGetMergeRedirectPath failed to check"...
0x180020aa7  mov     dword ptr [rsp+60h+var_40], r14d
0x180020aac  mov     r8d, 9DDh
0x180020ab2  lea     rdx, aSdbopendatabas; "SdbOpenDatabaseEx"
0x180020ab9  mov     ecx, 3
0x180020abe  call    AslLogCallPrintf
0x180020ac3  mov     esi, r14d
0x180020ac6  cmp     [rbp+var_28], 0
0x180020acb  jz      short loc_180020AE3
0x180020acd  mov     rcx, gs:60h
0x180020ad6  mov     rdx, [rbp+var_28]
0x180020ada  mov     rcx, [rcx+30h]
0x180020ade  call    AslFree
0x180020ae3  test    esi, esi
0x180020ae5  js      short loc_180020AED
0x180020ae7  cmp     qword ptr [rbx], 0
0x180020aeb  jnz     short loc_180020B20
0x180020aed  mov     rdx, r13
0x180020af0  mov     rcx, rbx
0x180020af3  call    AslFileMappingCreate
0x180020af8  test    eax, eax
0x180020afa  jns     short loc_180020B20
0x180020afc  lea     r9, aFailedToCreate; "Failed to create file mapping [%x]"
0x180020b03  mov     r8d, 0A12h
0x180020b09  lea     rdx, aSdbopendatabas; "SdbOpenDatabaseEx"
0x180020b10  mov     dword ptr [rsp+60h+var_40], eax
0x180020b14  mov     ecx, edi
0x180020b16  call    AslLogCallPrintf
0x180020b1b  jmp     loc_180020C28
0x180020b20  mov     rcx, [rbx]
0x180020b23  mov     rsi, [rcx+18h]
0x180020b27  lea     rax, [rsi-2Ah]
0x180020b2b  cmp     rax, 0FFFFFD5h
0x180020b31  ja      loc_180020C0D
0x180020b37  call    AslFileMappingEnsureMappedAsEx
0x180020b3c  test    eax, eax
0x180020b3e  jns     short loc_180020B4F
0x180020b40  lea     r9, aFailedToMapSdb; "Failed to map SDB [%x]"
0x180020b47  mov     r8d, 0A21h
0x180020b4d  jmp     short loc_180020B09
0x180020b4f  mov     dword ptr [rbx+10h], 0
0x180020b56  mov     [rbx+14h], esi
0x180020b59  mov     rcx, [rbx]
0x180020b5c  call    AslFileMappingGetViewBase
0x180020b61  mov     r9d, 0Ch
0x180020b67  mov     [rbx+8], rax
0x180020b6b  lea     r8, [rbp+var_18]
0x180020b6f  xor     edx, edx
0x180020b71  mov     rcx, rbx
0x180020b74  call    SdbpReadMappedData
0x180020b79  test    eax, eax
0x180020b7b  jnz     short loc_180020B8F
0x180020b7d  lea     r9, aFailedToReadDa_0; "Failed to read database header"
0x180020b84  mov     r8d, 0A2Eh
0x180020b8a  jmp     loc_180020C1A
0x180020b8f  mov     eax, [rbp+var_10]
0x180020b92  mov     ecx, 6662647Ah
0x180020b97  cmp     eax, 66626473h
0x180020b9c  jz      short loc_180020BBA
0x180020b9e  cmp     eax, ecx
0x180020ba0  jz      short loc_180020BBE
0x180020ba2  test    r12b, 2
0x180020ba6  jnz     short loc_180020BBA
0x180020ba8  lea     r9, aMagicDoesNotMa_0; "Magic does not match a valid value: 0x%"...
0x180020baf  mov     r8d, 0A3Bh
0x180020bb5  jmp     loc_180020B09
0x180020bba  cmp     eax, ecx
0x180020bbc  jnz     short loc_180020BF5
0x180020bbe  mov     r8d, r12d
0x180020bc1  lea     rcx, [rbp+var_20]
0x180020bc5  call    SdbpOpenCompressedDatabase
0x180020bca  test    eax, eax
0x180020bcc  jnz     short loc_180020BEF
0x180020bce  lea     r9, aSdbpopencompre; "SdbpOpenCompressedDatabase failed to op"...
0x180020bd5  mov     r8d, 0A41h
0x180020bdb  lea     rdx, aSdbopendatabas; "SdbOpenDatabaseEx"
0x180020be2  mov     ecx, edi
0x180020be4  call    AslLogCallPrintf
0x180020be9  mov     rbx, [rbp+var_20]
0x180020bed  jmp     short loc_180020C28
0x180020bef  mov     rbx, [rbp+var_20]
0x180020bf3  jmp     short loc_180020C08
0x180020bf5  mov     r8d, r12d
0x180020bf8  lea     rdx, [rbp+var_18]
0x180020bfc  mov     rcx, rbx
0x180020bff  call    SdbpValidateAndApplyCompatFlags
0x180020c04  test    eax, eax
0x180020c06  jz      short loc_180020C28
0x180020c08  mov     rax, rbx
0x180020c0b  jmp     short loc_180020C4C
0x180020c0d  lea     r9, aFailedToOpenSd; "Failed to open SDB - File size too larg"...
0x180020c14  mov     r8d, 0A1Bh
0x180020c1a  lea     rdx, aSdbopendatabas; "SdbOpenDatabaseEx"
0x180020c21  mov     ecx, edi
0x180020c23  call    AslLogCallPrintf
0x180020c28  test    rbx, rbx
0x180020c2b  jz      short loc_180020C4A
0x180020c2d  mov     rcx, [rbx]
0x180020c30  call    AslFileMappingDelete
0x180020c35  mov     rcx, gs:60h
0x180020c3e  mov     rdx, rbx
0x180020c41  mov     rcx, [rcx+30h]
0x180020c45  call    AslFree
0x180020c4a  xor     eax, eax
0x180020c4c  mov     rcx, [rbp+var_8]
0x180020c50  xor     rcx, rsp; StackCookie
0x180020c53  call    __security_check_cookie
0x180020c58  lea     r11, [rsp+60h+var_s0]
0x180020c5d  mov     rbx, [r11+38h]
0x180020c61  mov     rsi, [r11+48h]
0x180020c65  mov     rsp, r11
0x180020c68  pop     r14
0x180020c6a  pop     r13
0x180020c6c  pop     r12
0x180020c6e  pop     rdi
0x180020c6f  pop     rbp
0x180020c70  retn
```
