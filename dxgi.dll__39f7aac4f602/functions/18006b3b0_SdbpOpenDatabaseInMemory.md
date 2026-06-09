# SdbpOpenDatabaseInMemory

- ea: `0x18006b3b0`
- end: `0x18006b514`
- name: `SdbpOpenDatabaseInMemory`
- size: `356`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800adcc8`

## callees

- `0x180041774`
- `0x180042794`
- `0x18004281c`
- `0x18006b1c8`
- `0x18006b3b0`
- `0x18006b51c`
- `0x180075fa0`
- `0x1800ac42c`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18006b3f1`
- `ntdll!RtlAllocateHeap` at `0x18006b3f1`

## string_xrefs

- `0x18006b451`: `Can't read database header`
- `0x18006b40c`: `SdbpOpenDatabaseInMemory`
- `0x18006b45e`: `SdbpOpenDatabaseInMemory`
- `0x18006b4c0`: `SdbpOpenDatabaseInMemory`
- `0x18006b4fd`: `SdbpValidateAndApplyCompatFlags failed [%x]`

## pseudocode

```c
_DWORD *__fastcall SdbpOpenDatabaseInMemory(__int64 a1, int a2, unsigned int a3)
{
  _DWORD *Heap; // rax
  _DWORD *v7; // rbx
  int v9; // eax
  const char *v10; // r9
  __int64 v11; // r8
  __int64 v12; // [rsp+30h] [rbp-48h] BYREF
  int v13; // [rsp+38h] [rbp-40h]

  v12 = 0;
  v13 = 0;
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0xA80u);
  v7 = Heap;
  if ( !Heap )
  {
    AslLogCallPrintf(1, "SdbpOpenDatabaseInMemory", 2891, "Failed to allocate DB structure");
    return 0;
  }
  Heap[5] = a2;
  Heap[4] = 0;
  Heap[6] |= 1u;
  *((_QWORD *)Heap + 1) = a1;
  *(_QWORD *)Heap = 0;
  if ( !(unsigned int)SdbpReadMappedData(Heap, 0, &v12, 12) )
  {
    AslLogCallPrintf(1, "SdbpOpenDatabaseInMemory", 2902, "Can't read database header");
LABEL_5:
    AslFree(NtCurrentPeb()->ProcessHeap, v7);
    return 0;
  }
  if ( (unsigned int)Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline() )
  {
    v9 = v13;
    if ( v13 != 1717724275 && (a3 & 2) == 0 )
    {
      v10 = "Magic does not match a valid value: [0x%lx]";
      v11 = 2908;
LABEL_11:
      AslLogCallPrintf(1, "SdbpOpenDatabaseInMemory", v11, v10, v9);
      goto LABEL_5;
    }
  }
  if ( !(unsigned int)SdbpValidateAndApplyCompatFlags(v7, &v12, a3) )
    goto LABEL_5;
  if ( (unsigned int)Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline() )
  {
    v9 = SdbpValidateRootTagSizes(v7);
    if ( v9 < 0 )
    {
      v10 = "SdbpValidateAndApplyCompatFlags failed [%x]";
      v11 = 2920;
      goto LABEL_11;
    }
  }
  return v7;
}

```

## disassembly

```asm
0x18006b3b0  push    rbx
0x18006b3b2  push    rbp
0x18006b3b3  push    rsi
0x18006b3b4  push    rdi
0x18006b3b5  sub     rsp, 58h
0x18006b3b9  mov     rax, cs:__security_cookie
0x18006b3c0  xor     rax, rsp
0x18006b3c3  mov     [rsp+78h+var_38], rax
0x18006b3c8  xor     eax, eax
0x18006b3ca  mov     rbp, rcx
0x18006b3cd  mov     rcx, gs:60h
0x18006b3d6  mov     esi, r8d
0x18006b3d9  mov     edi, edx
0x18006b3db  mov     [rsp+78h+var_48], rax
0x18006b3e0  mov     r8d, 0A80h; Size
0x18006b3e6  mov     [rsp+78h+var_40], eax
0x18006b3ea  lea     edx, [rax+8]; Flags
0x18006b3ed  mov     rcx, [rcx+30h]; HeapHandle
0x18006b3f1  call    cs:__imp_RtlAllocateHeap
0x18006b3f7  mov     rbx, rax
0x18006b3fa  test    rax, rax
0x18006b3fd  jnz     short loc_18006B41D
0x18006b3ff  lea     r9, aFailedToAlloca_10; "Failed to allocate DB structure"
0x18006b406  mov     r8d, 0B4Bh
0x18006b40c  lea     rdx, aSdbpopendataba; "SdbpOpenDatabaseInMemory"
0x18006b413  lea     ecx, [rax+1]
0x18006b416  call    AslLogCallPrintf
0x18006b41b  jmp     short loc_18006B481
0x18006b41d  mov     [rax+14h], edi
0x18006b420  lea     r8, [rsp+78h+var_48]
0x18006b425  mov     edi, 1
0x18006b42a  mov     dword ptr [rax+10h], 0
0x18006b431  or      [rax+18h], edi
0x18006b434  xor     edx, edx
0x18006b436  mov     rcx, rbx
0x18006b439  mov     [rax+8], rbp
0x18006b43d  mov     qword ptr [rax], 0
0x18006b444  lea     r9d, [rdi+0Bh]
0x18006b448  call    SdbpReadMappedData
0x18006b44d  test    eax, eax
0x18006b44f  jnz     short loc_18006B499
0x18006b451  lea     r9, aCanTReadDataba; "Can't read database header"
0x18006b458  mov     r8d, 0B56h
0x18006b45e  lea     rdx, aSdbpopendataba; "SdbpOpenDatabaseInMemory"
0x18006b465  mov     ecx, edi
0x18006b467  call    AslLogCallPrintf
0x18006b46c  mov     rcx, gs:60h
0x18006b475  mov     rdx, rbx
0x18006b478  mov     rcx, [rcx+30h]
0x18006b47c  call    AslFree
0x18006b481  xor     eax, eax
0x18006b483  mov     rcx, [rsp+78h+var_38]
0x18006b488  xor     rcx, rsp; StackCookie
0x18006b48b  call    __security_check_cookie
0x18006b490  add     rsp, 58h
0x18006b494  pop     rdi
0x18006b495  pop     rsi
0x18006b496  pop     rbp
0x18006b497  pop     rbx
0x18006b498  retn
0x18006b499  call    Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline
0x18006b49e  test    eax, eax
0x18006b4a0  jz      short loc_18006B4D4
0x18006b4a2  mov     eax, [rsp+78h+var_40]
0x18006b4a6  cmp     eax, 66626473h
0x18006b4ab  jz      short loc_18006B4D4
0x18006b4ad  test    sil, 2
0x18006b4b1  jnz     short loc_18006B4D4
0x18006b4b3  lea     r9, aMagicDoesNotMa; "Magic does not match a valid value: [0x"...
0x18006b4ba  mov     r8d, 0B5Ch
0x18006b4c0  lea     rdx, aSdbpopendataba; "SdbpOpenDatabaseInMemory"
0x18006b4c7  mov     [rsp+78h+var_58], eax
0x18006b4cb  mov     ecx, edi
0x18006b4cd  call    AslLogCallPrintf
0x18006b4d2  jmp     short loc_18006B46C
0x18006b4d4  mov     r8d, esi
0x18006b4d7  lea     rdx, [rsp+78h+var_48]
0x18006b4dc  mov     rcx, rbx
0x18006b4df  call    SdbpValidateAndApplyCompatFlags
0x18006b4e4  test    eax, eax
0x18006b4e6  jz      short loc_18006B46C
0x18006b4e8  call    Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline
0x18006b4ed  test    eax, eax
0x18006b4ef  jz      short loc_18006B50C
0x18006b4f1  mov     rcx, rbx
0x18006b4f4  call    SdbpValidateRootTagSizes
0x18006b4f9  test    eax, eax
0x18006b4fb  jns     short loc_18006B50C
0x18006b4fd  lea     r9, aSdbpvalidatean_0; "SdbpValidateAndApplyCompatFlags failed "...
0x18006b504  mov     r8d, 0B68h
0x18006b50a  jmp     short loc_18006B4C0
0x18006b50c  mov     rax, rbx
0x18006b50f  jmp     loc_18006B483
```
