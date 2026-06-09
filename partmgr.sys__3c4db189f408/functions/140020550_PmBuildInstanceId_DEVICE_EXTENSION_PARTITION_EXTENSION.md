# PmBuildInstanceId(_DEVICE_EXTENSION *,_PARTITION_EXTENSION *)

- ea: `0x140020550`
- end: `0x1400206e8`
- name: `?PmBuildInstanceId@@YAJPEAU_DEVICE_EXTENSION@@PEAU_PARTITION_EXTENSION@@@Z`
- size: `408`
- prototype: `__int64 __fastcall(struct _DEVICE_EXTENSION *, struct _PARTITION_EXTENSION *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1400254c8`

## callees

- `0x140004504`
- `0x14000ae88`
- `0x140020550`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400206c5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400206c5`
- `ntoskrnl!ExAllocatePool2` at `0x1400205eb`
- `ntoskrnl!ExAllocatePool2` at `0x1400205eb`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x140020589`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x140020589`

## pseudocode

```c
__int64 __fastcall PmBuildInstanceId(const UNICODE_STRING *a1, struct _PARTITION_EXTENSION *a2)
{
  unsigned int v4; // r14d
  NTSTATUS v5; // ebx
  unsigned int v6; // eax
  __int64 v7; // r8
  __int16 v8; // cx
  wchar_t *Pool2; // r12

  if ( (ScReadNoFence((unsigned int *)a2 + 10) & 0x200) != 0 )
  {
    v4 = 0;
    v5 = RtlDuplicateUnicodeString(1u, a1 + 30, (PUNICODE_STRING)a2 + 3);
    if ( v5 >= 0 )
    {
      v6 = *((unsigned __int16 *)a2 + 24) >> 1;
      if ( v6 )
      {
        do
        {
          v7 = *((_QWORD *)a2 + 7);
          v8 = *(_WORD *)(v7 + 2LL * v4);
          if ( v8 == 47 || v8 == 92 )
            *(_WORD *)(v7 + 2LL * v4) = 95;
          ++v4;
        }
        while ( v4 < v6 );
      }
    }
  }
  else
  {
    Pool2 = (wchar_t *)ExAllocatePool2(258, 112, 1178758480);
    if ( Pool2 )
    {
      v5 = RtlStringCbPrintfW(
             Pool2,
             0x70u,
             L"{%08lx-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x}#%016I64X",
             LODWORD(a1[13].Buffer),
             WORD2(a1[13].Buffer),
             HIWORD(a1[13].Buffer),
             LOBYTE(a1[14].Length),
             HIBYTE(a1[14].Length),
             LOBYTE(a1[14].MaximumLength),
             HIBYTE(a1[14].MaximumLength),
             *((unsigned __int8 *)&a1[14].MaximumLength + 2),
             *((unsigned __int8 *)&a1[14].MaximumLength + 3),
             *((unsigned __int8 *)&a1[14].MaximumLength + 4),
             *((unsigned __int8 *)&a1[14].MaximumLength + 5),
             *((_QWORD *)a2 + 22));
      if ( v5 < 0 )
      {
        ExFreePoolWithTag(Pool2, 0);
      }
      else
      {
        *((_DWORD *)a2 + 12) = 7340142;
        *((_QWORD *)a2 + 7) = Pool2;
      }
    }
    else
    {
      return (unsigned int)-1073741670;
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140020550  push    rbx
0x140020552  push    rbp
0x140020553  push    rsi
0x140020554  push    rdi
0x140020555  push    r12
0x140020557  push    r13
0x140020559  push    r14
0x14002055b  push    r15
0x14002055d  sub     rsp, 88h
0x140020564  mov     r13, rcx
0x140020567  mov     r15, rdx
0x14002056a  lea     rcx, [rdx+28h]; unsigned int *
0x14002056e  call    ?ScReadNoFence@@YAKPEAK@Z; ScReadNoFence(ulong *)
0x140020573  bt      eax, 9
0x140020577  jnb     short loc_1400205DB
0x140020579  lea     rdx, [r13+1E0h]; StringIn
0x140020580  mov     ecx, 1; Flags
0x140020585  lea     r8, [r15+30h]; StringOut
0x140020589  call    cs:__imp_RtlDuplicateUnicodeString
0x140020590  nop     dword ptr [rax+rax+00h]
0x140020595  xor     r14d, r14d
0x140020598  mov     ebx, eax
0x14002059a  test    eax, eax
0x14002059c  js      loc_1400206D1
0x1400205a2  movzx   eax, word ptr [r15+30h]
0x1400205a7  shr     eax, 1
0x1400205a9  jz      loc_1400206D1
0x1400205af  mov     r8, [r15+38h]
0x1400205b3  mov     edx, r14d
0x1400205b6  movzx   ecx, word ptr [r8+rdx*2]
0x1400205bb  cmp     cx, 2Fh ; '/'
0x1400205bf  jz      short loc_1400205C7
0x1400205c1  cmp     cx, 5Ch ; '\'
0x1400205c5  jnz     short loc_1400205CE
0x1400205c7  mov     word ptr [r8+rdx*2], 5Fh ; '_'
0x1400205ce  inc     r14d
0x1400205d1  cmp     r14d, eax
0x1400205d4  jb      short loc_1400205AF
0x1400205d6  jmp     loc_1400206D1
0x1400205db  mov     edx, 70h ; 'p'
0x1400205e0  mov     ecx, 102h
0x1400205e5  mov     r8d, 46426D50h
0x1400205eb  call    cs:__imp_ExAllocatePool2
0x1400205f2  nop     dword ptr [rax+rax+00h]
0x1400205f7  mov     r12, rax
0x1400205fa  test    rax, rax
0x1400205fd  jnz     short loc_140020609
0x1400205ff  mov     ebx, 0C000009Ah
0x140020604  jmp     loc_1400206D1
0x140020609  movzx   ecx, byte ptr [r13+0E7h]
0x140020611  movzx   edx, byte ptr [r13+0E6h]
0x140020619  movzx   r8d, byte ptr [r13+0E5h]
0x140020621  movzx   r9d, byte ptr [r13+0E4h]
0x140020629  mov     rax, [r15+0B0h]
0x140020630  movzx   r10d, byte ptr [r13+0E3h]
0x140020638  movzx   r11d, byte ptr [r13+0E2h]
0x140020640  movzx   ebx, byte ptr [r13+0E1h]
0x140020648  movzx   edi, byte ptr [r13+0E0h]
0x140020650  movzx   esi, word ptr [r13+0DEh]
0x140020658  movzx   ebp, word ptr [r13+0DCh]
0x140020660  mov     [rsp+0C8h+var_58], rax
0x140020665  mov     [rsp+0C8h+var_60], ecx
0x140020669  mov     rcx, r12; pszDest
0x14002066c  mov     [rsp+0C8h+var_68], edx
0x140020670  mov     edx, 70h ; 'p'; cbDest
0x140020675  mov     [rsp+0C8h+var_70], r8d
0x14002067a  lea     r8, a08lx04x04x02x0; "{%08lx-%04x-%04x-%02x%02x-%02x%02x%02x%"...
0x140020681  mov     [rsp+0C8h+var_78], r9d
0x140020686  mov     r9d, [r13+0D8h]
0x14002068d  mov     [rsp+0C8h+var_80], r10d
0x140020692  mov     [rsp+0C8h+var_88], r11d
0x140020697  mov     [rsp+0C8h+var_90], ebx
0x14002069b  mov     [rsp+0C8h+var_98], edi
0x14002069f  mov     [rsp+0C8h+var_A0], esi
0x1400206a3  mov     [rsp+0C8h+var_A8], ebp
0x1400206a7  call    RtlStringCbPrintfW
0x1400206ac  mov     ebx, eax
0x1400206ae  test    eax, eax
0x1400206b0  js      short loc_1400206C0
0x1400206b2  mov     dword ptr [r15+30h], 70006Eh
0x1400206ba  mov     [r15+38h], r12
0x1400206be  jmp     short loc_1400206D1
0x1400206c0  xor     edx, edx; Tag
0x1400206c2  mov     rcx, r12; P
0x1400206c5  call    cs:__imp_ExFreePoolWithTag
0x1400206cc  nop     dword ptr [rax+rax+00h]
0x1400206d1  mov     eax, ebx
0x1400206d3  add     rsp, 88h
0x1400206da  pop     r15
0x1400206dc  pop     r14
0x1400206de  pop     r13
0x1400206e0  pop     r12
0x1400206e2  pop     rdi
0x1400206e3  pop     rsi
0x1400206e4  pop     rbp
0x1400206e5  pop     rbx
0x1400206e6  retn
```
