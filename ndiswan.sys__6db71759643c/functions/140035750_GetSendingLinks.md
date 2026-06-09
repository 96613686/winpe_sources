# GetSendingLinks

- ea: `0x140035750`
- end: `0x14003594b`
- name: `GetSendingLinks`
- size: `507`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140030144`
- `0x1400312a0`

## callees

- `0x140035750`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140035797`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14003588f`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400358ed`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140035797`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14003588f`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400358ed`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400357ec`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400358be`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14003591c`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400357ec`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400358be`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14003591c`

## pseudocode

```c
__int64 __fastcall GetSendingLinks(__int64 a1, int a2, __int64 a3)
{
  _QWORD *v3; // r14
  unsigned int v4; // ebp
  _QWORD *v7; // rbx
  _QWORD *v8; // r12
  _QWORD *v9; // rcx
  _QWORD *v10; // rcx
  _QWORD *v11; // rax
  _QWORD *v13; // rdx
  _QWORD *v14; // rdx

  v3 = *(_QWORD **)(a1 + 88);
  v4 = 0;
  if ( v3 )
  {
    v7 = *(_QWORD **)(a1 + 88);
    v8 = v7;
    if ( a2 == 1 )
    {
      do
      {
        KeAcquireSpinLockAtDpcLevel(v7 + 92);
        if ( *((_DWORD *)v7 + 5) == 2 && *((_BYTE *)v7 + 200) && *((_BYTE *)v7 + 201) )
        {
          v13 = *(_QWORD **)(a3 + 8);
          if ( *v13 != a3 )
LABEL_34:
            __fastfail(3u);
          v3 = v7;
          v7[30] = a3;
          v7[31] = v13;
          *v13 = v7 + 30;
          *(_QWORD *)(a3 + 8) = v7 + 30;
          ++*((_DWORD *)v7 + 7);
          ++v4;
        }
        KeReleaseSpinLockFromDpcLevel(v7 + 92);
        v10 = (_QWORD *)(a1 + 48);
        v7 = (_QWORD *)*v7;
        if ( v7 == (_QWORD *)(a1 + 48) )
          v7 = (_QWORD *)*v10;
      }
      while ( v7 != v8 );
    }
    else if ( (*(_DWORD *)(a1 + 16) & 0x400) != 0 )
    {
      do
      {
        KeAcquireSpinLockAtDpcLevel(v7 + 92);
        if ( *((_DWORD *)v7 + 5) == 2 && *((_BYTE *)v7 + 200) && *((_DWORD *)v7 + 51) )
        {
          v14 = *(_QWORD **)(a3 + 8);
          if ( *v14 != a3 )
            goto LABEL_34;
          v3 = v7;
          v7[30] = a3;
          v7[31] = v14;
          *v14 = v7 + 30;
          *(_QWORD *)(a3 + 8) = v7 + 30;
          ++*((_DWORD *)v7 + 7);
          ++v4;
        }
        KeReleaseSpinLockFromDpcLevel(v7 + 92);
        v10 = (_QWORD *)(a1 + 48);
        v7 = (_QWORD *)*v7;
        if ( v7 == (_QWORD *)(a1 + 48) )
          v7 = (_QWORD *)*v10;
      }
      while ( v7 != v8 );
    }
    else
    {
      do
      {
        KeAcquireSpinLockAtDpcLevel(v7 + 92);
        if ( *((_DWORD *)v7 + 5) == 2 && *((_BYTE *)v7 + 200) && *((_BYTE *)v7 + 201) )
        {
          v9 = *(_QWORD **)(a3 + 8);
          if ( *v9 != a3 )
            goto LABEL_34;
          v3 = v7;
          v7[30] = a3;
          v7[31] = v9;
          *v9 = v7 + 30;
          *(_QWORD *)(a3 + 8) = v7 + 30;
          ++*((_DWORD *)v7 + 7);
          ++v4;
        }
        KeReleaseSpinLockFromDpcLevel(v7 + 92);
        v7 = (_QWORD *)*v7;
        v10 = (_QWORD *)(a1 + 48);
        if ( v7 == (_QWORD *)(a1 + 48) )
          v7 = (_QWORD *)*v10;
      }
      while ( v7 != v8 );
    }
    v11 = (_QWORD *)*v3;
    if ( (_QWORD *)*v3 == v10 )
      v11 = (_QWORD *)*v10;
    *(_QWORD *)(a1 + 88) = v11;
  }
  return v4;
}

```

## disassembly

```asm
0x140035750  push    rbx
0x140035752  push    rbp
0x140035753  push    rsi
0x140035754  push    rdi
0x140035755  push    r12
0x140035757  push    r14
0x140035759  push    r15
0x14003575b  sub     rsp, 20h
0x14003575f  mov     r14, [rcx+58h]
0x140035763  xor     ebp, ebp
0x140035765  mov     r15, r8
0x140035768  mov     rdi, rcx
0x14003576b  test    r14, r14
0x14003576e  jz      loc_14003581B
0x140035774  mov     rbx, r14
0x140035777  mov     r12, r14
0x14003577a  cmp     edx, 1
0x14003577d  jz      loc_140035888
0x140035783  test    dword ptr [rcx+10h], 400h
0x14003578a  jnz     loc_1400358E6
0x140035790  lea     rcx, [rbx+2E0h]; SpinLock
0x140035797  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x14003579e  nop     dword ptr [rax+rax+00h]
0x1400357a3  cmp     dword ptr [rbx+14h], 2
0x1400357a7  jnz     short loc_1400357E5
0x1400357a9  cmp     byte ptr [rbx+0C8h], 0
0x1400357b0  jz      short loc_1400357E5
0x1400357b2  cmp     byte ptr [rbx+0C9h], 0
0x1400357b9  jz      short loc_1400357E5
0x1400357bb  mov     rcx, [r15+8]
0x1400357bf  cmp     [rcx], r15
0x1400357c2  jnz     loc_140035944
0x1400357c8  lea     rax, [rbx+0F0h]
0x1400357cf  mov     r14, rbx
0x1400357d2  mov     [rax], r15
0x1400357d5  mov     [rax+8], rcx
0x1400357d9  mov     [rcx], rax
0x1400357dc  mov     [r15+8], rax
0x1400357e0  inc     dword ptr [rbx+1Ch]
0x1400357e3  inc     ebp
0x1400357e5  lea     rcx, [rbx+2E0h]; SpinLock
0x1400357ec  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x1400357f3  nop     dword ptr [rax+rax+00h]
0x1400357f8  mov     rbx, [rbx]
0x1400357fb  lea     rcx, [rdi+30h]
0x1400357ff  cmp     rbx, rcx
0x140035802  jnz     short loc_140035807
0x140035804  mov     rbx, [rcx]
0x140035807  cmp     rbx, r12
0x14003580a  jnz     short loc_140035790
0x14003580c  mov     rax, [r14]
0x14003580f  cmp     rax, rcx
0x140035812  jnz     short loc_140035817
0x140035814  mov     rax, [rcx]
0x140035817  mov     [rdi+58h], rax
0x14003581b  mov     eax, ebp
0x14003581d  add     rsp, 20h
0x140035821  pop     r15
0x140035823  pop     r14
0x140035825  pop     r12
0x140035827  pop     rdi
0x140035828  pop     rsi
0x140035829  pop     rbp
0x14003582a  pop     rbx
0x14003582b  retn
0x14003582d  mov     rdx, [r15+8]
0x140035831  cmp     [rdx], r15
0x140035834  jnz     loc_140035944
0x14003583a  lea     rax, [rbx+0F0h]
0x140035841  mov     r14, rbx
0x140035844  mov     [rax], r15
0x140035847  mov     [rax+8], rdx
0x14003584b  mov     [rdx], rax
0x14003584e  mov     [r15+8], rax
0x140035852  inc     dword ptr [rbx+1Ch]
0x140035855  inc     ebp
0x140035857  jmp     short loc_1400358B7
0x140035859  mov     rdx, [r15+8]
0x14003585d  cmp     [rdx], r15
0x140035860  jnz     loc_140035944
0x140035866  lea     rax, [rbx+0F0h]
0x14003586d  mov     r14, rbx
0x140035870  mov     [rax], r15
0x140035873  mov     [rax+8], rdx
0x140035877  mov     [rdx], rax
0x14003587a  mov     [r15+8], rax
0x14003587e  inc     dword ptr [rbx+1Ch]
0x140035881  inc     ebp
0x140035883  jmp     loc_140035915
0x140035888  lea     rcx, [rbx+2E0h]; SpinLock
0x14003588f  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x140035896  nop     dword ptr [rax+rax+00h]
0x14003589b  cmp     dword ptr [rbx+14h], 2
0x14003589f  jnz     short loc_1400358B7
0x1400358a1  cmp     byte ptr [rbx+0C8h], 0
0x1400358a8  jz      short loc_1400358B7
0x1400358aa  cmp     byte ptr [rbx+0C9h], 0
0x1400358b1  jnz     loc_14003582D
0x1400358b7  lea     rcx, [rbx+2E0h]; SpinLock
0x1400358be  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x1400358c5  nop     dword ptr [rax+rax+00h]
0x1400358ca  mov     rax, [rbx]
0x1400358cd  lea     rcx, [rdi+30h]
0x1400358d1  mov     rbx, rax
0x1400358d4  cmp     rax, rcx
0x1400358d7  jnz     short loc_1400358DC
0x1400358d9  mov     rbx, [rcx]
0x1400358dc  cmp     rbx, r12
0x1400358df  jnz     short loc_140035888
0x1400358e1  jmp     loc_14003580C
0x1400358e6  lea     rcx, [rbx+2E0h]; SpinLock
0x1400358ed  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x1400358f4  nop     dword ptr [rax+rax+00h]
0x1400358f9  cmp     dword ptr [rbx+14h], 2
0x1400358fd  jnz     short loc_140035915
0x1400358ff  cmp     byte ptr [rbx+0C8h], 0
0x140035906  jz      short loc_140035915
0x140035908  cmp     dword ptr [rbx+0CCh], 0
0x14003590f  jnz     loc_140035859
0x140035915  lea     rcx, [rbx+2E0h]; SpinLock
0x14003591c  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140035923  nop     dword ptr [rax+rax+00h]
0x140035928  mov     rax, [rbx]
0x14003592b  lea     rcx, [rdi+30h]
0x14003592f  mov     rbx, rax
0x140035932  cmp     rax, rcx
0x140035935  jnz     short loc_14003593A
0x140035937  mov     rbx, [rcx]
0x14003593a  cmp     rbx, r12
0x14003593d  jnz     short loc_1400358E6
0x14003593f  jmp     loc_14003580C
0x140035944  mov     ecx, 3
0x140035949  int     29h; Win8: RtlFailFast(ecx)
```
