# PrepareThreads(DIRECTCOLORCONVFRM *)

- ea: `0x180011500`
- end: `0x1800115a6`
- name: `?PrepareThreads@@YAXPEAUDIRECTCOLORCONVFRM@@@Z`
- size: `166`
- prototype: `void __fastcall(struct DIRECTCOLORCONVFRM *)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180019ea4`
- `0x18001f874`
- `0x180028b6c`

## callees

- `0x180009bf8`
- `0x180010f28`
- `0x180011500`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180011536`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180011536`

## pseudocode

```c
void __fastcall PrepareThreads(struct DIRECTCOLORCONVFRM *a1)
{
  signed __int32 v2; // eax
  signed __int32 v3; // eax
  unsigned int v4; // edx

  *((_DWORD *)a1 + 3659) = 0;
  while ( 1 )
  {
    v2 = _InterlockedCompareExchange(&dword_18003AAB4, 1, 0);
    if ( !v2 )
      break;
    v3 = v2 - 1;
    if ( v3 )
    {
      if ( v3 == 1 )
        goto LABEL_8;
    }
    else
    {
      Sleep(1u);
    }
  }
  InitLogicProcTableInternal();
  _InterlockedIncrement(&dword_18003AAB4);
LABEL_8:
  v4 = dword_18003AAE4;
  if ( (unsigned int)(*((_DWORD *)a1 + 3850) - 1) <= 3 )
    v4 = *((_DWORD *)a1 + 3850);
  if ( v4 == 3 || v4 > 4 )
    v4 = 4;
  *((_DWORD *)a1 + 3660) = 2 - (v4 < 2);
  if ( *(_DWORD *)(*(_QWORD *)a1 + 16LL) == 961893977 )
    *((_DWORD *)a1 + 3660) = 1;
  *((_DWORD *)a1 + 3658) = 1;
  InitThreads(a1);
}

```

## disassembly

```asm
0x180011500  mov     [rsp+arg_0], rbx
0x180011505  push    rdi
0x180011506  sub     rsp, 20h
0x18001150a  mov     rbx, rcx
0x18001150d  mov     dword ptr [rcx+392Ch], 0
0x180011517  mov     edi, 1
0x18001151c  xor     eax, eax
0x18001151e  lock cmpxchg cs:dword_18003AAB4, edi
0x180011526  test    eax, eax
0x180011528  jz      short loc_18001153E
0x18001152a  sub     eax, edi
0x18001152c  jz      short loc_180011534
0x18001152e  cmp     eax, edi
0x180011530  jnz     short loc_18001151C
0x180011532  jmp     short loc_18001154A
0x180011534  mov     ecx, edi; dwMilliseconds
0x180011536  call    cs:__imp_Sleep
0x18001153c  jmp     short loc_18001151C
0x18001153e  call    InitLogicProcTableInternal
0x180011543  lock inc cs:dword_18003AAB4
0x18001154a  mov     ecx, [rbx+3C28h]
0x180011550  mov     edx, cs:dword_18003AAE4
0x180011556  lea     eax, [rcx-1]
0x180011559  cmp     eax, 3
0x18001155c  cmovbe  edx, ecx
0x18001155f  cmp     edx, 3
0x180011562  jz      short loc_180011569
0x180011564  cmp     edx, 4
0x180011567  jbe     short loc_18001156E
0x180011569  mov     edx, 4
0x18001156e  cmp     edx, 2
0x180011571  sbb     eax, eax
0x180011573  add     eax, 2
0x180011576  mov     [rbx+3930h], eax
0x18001157c  mov     rax, [rbx]
0x18001157f  cmp     dword ptr [rax+10h], 39555659h
0x180011586  jnz     short loc_18001158E
0x180011588  mov     [rbx+3930h], edi
0x18001158e  mov     rcx, rbx; struct DIRECTCOLORCONVFRM *
0x180011591  mov     [rbx+3928h], edi
0x180011597  mov     rbx, [rsp+28h+arg_0]
0x18001159c  add     rsp, 20h
0x1800115a0  pop     rdi
0x1800115a1  jmp     ?InitThreads@@YAHPEAUDIRECTCOLORCONVFRM@@@Z; InitThreads(DIRECTCOLORCONVFRM *)
```
