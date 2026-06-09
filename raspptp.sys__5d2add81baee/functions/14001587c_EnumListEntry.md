# EnumListEntry

- ea: `0x14001587c`
- end: `0x1400159e9`
- name: `EnumListEntry`
- size: `365`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x140011838`
- `0x140011d04`
- `0x1400122b0`
- `0x1400133d0`
- `0x140013954`

## callees

- `0x140003e08`
- `0x14001587c`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x1400159c7`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400159c7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001589d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001589d`

## pseudocode

```c
volatile signed __int32 *__fastcall EnumListEntry(volatile signed __int32 *a1, __int64 a2, __int64 a3, int a4)
{
  volatile signed __int32 *v4; // rbx
  volatile signed __int32 *v9; // rax
  volatile signed __int32 *v10; // rax
  __int64 v11; // rcx
  volatile signed __int32 *v12; // rcx
  volatile signed __int32 **v13; // rcx
  __int64 v14; // rcx
  volatile signed __int32 *v15; // rax

  v4 = 0;
  if ( a3 )
    *(_BYTE *)(a3 + 8) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)a3);
  do
  {
    v9 = *(volatile signed __int32 **)a2;
    if ( *(_QWORD *)a2 )
    {
      if ( *((_QWORD *)v9 + 1) != a2 )
        goto LABEL_32;
      v13 = *(volatile signed __int32 ***)(a2 + 8);
      if ( v9 == a1 )
      {
        if ( *v13 != (volatile signed __int32 *)a2 )
LABEL_32:
          __fastfail(3u);
        *v13 = v9;
        *((_QWORD *)v9 + 1) = v13;
        *(_QWORD *)(a2 + 8) = 0;
        *(_QWORD *)a2 = 0;
LABEL_28:
        v4 = 0;
        goto LABEL_29;
      }
      if ( *v13 != (volatile signed __int32 *)a2 )
        goto LABEL_32;
      *v13 = v9;
      *((_QWORD *)v9 + 1) = v13;
      v14 = *(_QWORD *)v9;
      if ( *(volatile signed __int32 **)(*(_QWORD *)v9 + 8LL) != v9 )
        goto LABEL_32;
      *(_QWORD *)a2 = v14;
      v4 = v9;
      *(_QWORD *)(a2 + 8) = v9;
      *(_QWORD *)(v14 + 8) = a2;
      v12 = v9 + 4;
      *(_QWORD *)v9 = a2;
    }
    else
    {
      v10 = *(volatile signed __int32 **)a1;
      if ( *(volatile signed __int32 **)a1 != a1 )
      {
        v11 = *(_QWORD *)v10;
        if ( *(volatile signed __int32 **)(*(_QWORD *)v10 + 8LL) != v10 )
          goto LABEL_32;
        *(_QWORD *)a2 = v11;
        v4 = v10;
        *(_QWORD *)(a2 + 8) = v10;
        *(_QWORD *)(v11 + 8) = a2;
        *(_QWORD *)v10 = a2;
      }
      v12 = v4 + 4;
      if ( !v4 )
        goto LABEL_29;
    }
  }
  while ( *v12 == 1297436229 );
  if ( !a4 )
  {
    v15 = v4 - 4;
    if ( v4 != (volatile signed __int32 *)16 && *((_DWORD *)v15 + 12) == 1129337936 && *v15 )
    {
      _InterlockedIncrement(v15);
      goto LABEL_29;
    }
    goto LABEL_28;
  }
  if ( a4 == 1 )
  {
    _InterlockedIncrement(v12);
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
         && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
         && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF_((__int64)WPP_GLOBAL_Control->AttachedDevice, 0xDu, (__int64)WPP_ca61754c7b3436dd8b10c3936da565f6_Traceguids);
  }
LABEL_29:
  if ( a3 )
    KeReleaseSpinLock((PKSPIN_LOCK)a3, *(_BYTE *)(a3 + 8));
  return v4;
}

```

## disassembly

```asm
0x14001587c  push    rbx
0x14001587e  push    rbp
0x14001587f  push    rsi
0x140015880  push    rdi
0x140015881  push    r14
0x140015883  sub     rsp, 20h
0x140015887  xor     ebx, ebx
0x140015889  mov     ebp, r9d
0x14001588c  mov     rsi, r8
0x14001588f  mov     rdi, rdx
0x140015892  mov     r14, rcx
0x140015895  test    r8, r8
0x140015898  jz      short loc_1400158AC
0x14001589a  mov     rcx, r8; SpinLock
0x14001589d  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400158a4  nop     dword ptr [rax+rax+00h]
0x1400158a9  mov     [rsi+8], al
0x1400158ac  mov     rax, [rdi]
0x1400158af  test    rax, rax
0x1400158b2  jnz     short loc_1400158E9
0x1400158b4  mov     rax, [r14]
0x1400158b7  cmp     rax, r14
0x1400158ba  jz      short loc_1400158DA
0x1400158bc  mov     rcx, [rax]
0x1400158bf  cmp     [rcx+8], rax
0x1400158c3  jnz     loc_1400159E2
0x1400158c9  mov     [rdi], rcx
0x1400158cc  mov     rbx, rax
0x1400158cf  mov     [rdi+8], rax
0x1400158d3  mov     [rcx+8], rdi
0x1400158d7  mov     [rax], rdi
0x1400158da  lea     rcx, [rbx+10h]
0x1400158de  test    rbx, rbx
0x1400158e1  jz      loc_1400159BC
0x1400158e7  jmp     short loc_140015932
0x1400158e9  cmp     [rax+8], rdi
0x1400158ed  jnz     loc_1400159E2
0x1400158f3  mov     rcx, [rdi+8]
0x1400158f7  cmp     rax, r14
0x1400158fa  jz      loc_14001599F
0x140015900  cmp     [rcx], rdi
0x140015903  jnz     loc_1400159E2
0x140015909  mov     [rcx], rax
0x14001590c  mov     [rax+8], rcx
0x140015910  mov     rcx, [rax]
0x140015913  cmp     [rcx+8], rax
0x140015917  jnz     loc_1400159E2
0x14001591d  mov     [rdi], rcx
0x140015920  mov     rbx, rax
0x140015923  mov     [rdi+8], rax
0x140015927  mov     [rcx+8], rdi
0x14001592b  lea     rcx, [rax+10h]
0x14001592f  mov     [rax], rdi
0x140015932  cmp     dword ptr [rcx], 4D554E45h
0x140015938  jz      loc_1400158AC
0x14001593e  test    ebp, ebp
0x140015940  jz      short loc_140015983
0x140015942  cmp     ebp, 1
0x140015945  jz      short loc_14001597E
0x140015947  mov     rcx, cs:WPP_GLOBAL_Control
0x14001594e  lea     rax, WPP_GLOBAL_Control
0x140015955  cmp     rcx, rax
0x140015958  jz      short loc_1400159BC
0x14001595a  mov     eax, [rcx+2Ch]
0x14001595d  test    al, 1
0x14001595f  jz      short loc_1400159BC
0x140015961  cmp     byte ptr [rcx+29h], 1
0x140015965  jb      short loc_1400159BC
0x140015967  mov     rcx, [rcx+18h]
0x14001596b  lea     r8, WPP_ca61754c7b3436dd8b10c3936da565f6_Traceguids
0x140015972  mov     edx, 0Dh
0x140015977  call    WPP_SF_
0x14001597c  jmp     short loc_1400159BC
0x14001597e  lock inc dword ptr [rcx]
0x140015981  jmp     short loc_1400159BC
0x140015983  lea     rax, [rbx-10h]
0x140015987  test    rax, rax
0x14001598a  jz      short loc_1400159BA
0x14001598c  cmp     dword ptr [rax+30h], 43505450h
0x140015993  jnz     short loc_1400159BA
0x140015995  cmp     dword ptr [rax], 1
0x140015998  jb      short loc_1400159BA
0x14001599a  lock inc dword ptr [rax]
0x14001599d  jmp     short loc_1400159BC
0x14001599f  cmp     [rcx], rdi
0x1400159a2  jnz     short loc_1400159E2
0x1400159a4  mov     [rcx], rax
0x1400159a7  mov     [rax+8], rcx
0x1400159ab  mov     qword ptr [rdi+8], 0
0x1400159b3  mov     qword ptr [rdi], 0
0x1400159ba  xor     ebx, ebx
0x1400159bc  test    rsi, rsi
0x1400159bf  jz      short loc_1400159D3
0x1400159c1  mov     dl, [rsi+8]; NewIrql
0x1400159c4  mov     rcx, rsi; SpinLock
0x1400159c7  call    cs:__imp_KeReleaseSpinLock
0x1400159ce  nop     dword ptr [rax+rax+00h]
0x1400159d3  mov     rax, rbx
0x1400159d6  add     rsp, 20h
0x1400159da  pop     r14
0x1400159dc  pop     rdi
0x1400159dd  pop     rsi
0x1400159de  pop     rbp
0x1400159df  pop     rbx
0x1400159e0  retn
0x1400159e2  mov     ecx, 3
0x1400159e7  int     29h; Win8: RtlFailFast(ecx)
```
