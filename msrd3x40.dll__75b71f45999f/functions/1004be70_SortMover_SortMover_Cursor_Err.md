# SortMover::SortMover(Cursor *,Err &)

- ea: `0x1004be70`
- end: `0x1004c00b`
- name: `??0SortMover@@QAE@PAVCursor@@AAVErr@@@Z`
- size: `411`
- prototype: `SortMover *__thiscall(SortMover *__hidden this, struct Cursor *, struct Err *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x10019240`

## callees

- `0x1000eb60`
- `0x100336e0`
- `0x10038630`
- `0x10045450`
- `0x1004bd40`
- `0x1004be70`
- `0x1005e3b0`
- `0x1005e74d`
- `0x1005e798`
- `0x1005e7e8`
- `0x1005f064`

## pseudocode

```c
SortMover *__thiscall SortMover::SortMover(SortMover *this, struct Cursor *a2, void **a3)
{
  int v4; // eax
  int v5; // ecx
  int v6; // eax
  int v7; // ebx
  Sort *v8; // eax
  int v9; // eax
  Sort *Block; // [esp+10h] [ebp-14h]

  *(_DWORD *)this = &SortMover::`vftable';
  *((_DWORD *)this + 9) = 0;
  *((_DWORD *)this + 11) = (char *)this + 56;
  *((_DWORD *)this + 10) = 0;
  *((_DWORD *)this + 12) = 0;
  *((_DWORD *)this + 13) = 32;
  *((_DWORD *)this + 23) = 0;
  *((_DWORD *)this + 24) = (char *)this + 108;
  *((_DWORD *)this + 25) = 0;
  *((_DWORD *)this + 26) = 32;
  *((_DWORD *)this + 1) = a2;
  *((_DWORD *)this + 2) = 0;
  *((_DWORD *)this + 5) = -1;
  *((_DWORD *)this + 22) = 0;
  v4 = (*(int (__thiscall **)(struct Cursor *))(*(_DWORD *)a2 + 60))(a2);
  if ( *(int *)(v4 + 24) <= 0 || (v5 = *(_DWORD *)(v4 + 1524), v5 == -1) )
    v6 = 0;
  else
    v6 = *(_DWORD *)(v4 + 4 * v5 + 1396);
  v7 = *(_BYTE *)(*(_DWORD *)(v6 + 8) + 64) & 1;
  Block = (Sort *)operator new(0x5E4u);
  v8 = Sort::Sort(Block);
  *((_DWORD *)this + 3) = v8;
  if ( v8 )
  {
    v9 = (*(int (__thiscall **)(struct Cursor *))(*(_DWORD *)a2 + 56))(a2);
    Sort::Open(*((_DWORD *)this + 3), *(_DWORD *)(v9 + 12), v7, 0x40000, a3);
    ++**((_DWORD **)this + 3);
    *((_DWORD *)this + 4) = *(_DWORD *)(*((_DWORD *)this + 3) + 24);
  }
  else if ( (int)*a3 < 8 )
  {
    if ( ((unsigned int)*a3 & 0xFFFFFFFE) != 0 )
    {
      if ( a3[3] )
        operator delete[](a3[3]);
      if ( a3[4] )
        operator delete[](a3[4]);
    }
    *a3 = (void *)8;
    a3[1] = (void *)-1011;
    a3[2] = 0;
    a3[3] = 0;
    a3[4] = 0;
  }
  return this;
}

```

## disassembly

```asm
0x1004be70  mov     edi, edi
0x1004be72  push    ebp
0x1004be73  mov     ebp, esp
0x1004be75  push    0FFFFFFFFh
0x1004be77  push    offset ??0SortMover@@QAE@PAVCursor@@AAVErr@@@Z_SEH
0x1004be7c  mov     eax, large fs:0
0x1004be82  push    eax
0x1004be83  sub     esp, 8
0x1004be86  push    ebx
0x1004be87  push    esi
0x1004be88  push    edi; unsigned int
0x1004be89  mov     eax, ___security_cookie
0x1004be8e  xor     eax, ebp
0x1004be90  push    eax; void *
0x1004be91  lea     eax, [ebp+var_C]
0x1004be94  mov     large fs:0, eax
0x1004be9a  mov     edi, ecx
0x1004be9c  mov     [ebp+var_10], edi
0x1004be9f  mov     [ebp+var_4], 0
0x1004bea6  lea     eax, [edi+38h]
0x1004bea9  mov     dword ptr [edi], offset ??_7SortMover@@6B@; const SortMover::`vftable'
0x1004beaf  mov     dword ptr [edi+24h], 0
0x1004beb6  mov     [edi+2Ch], eax
0x1004beb9  mov     dword ptr [edi+28h], 0
0x1004bec0  mov     dword ptr [edi+30h], 0
0x1004bec7  mov     dword ptr [edi+34h], 20h ; ' '
0x1004bece  lea     eax, [edi+6Ch]
0x1004bed1  mov     dword ptr [edi+5Ch], 0
0x1004bed8  mov     [edi+60h], eax
0x1004bedb  mov     dword ptr [edi+64h], 0
0x1004bee2  mov     dword ptr [edi+68h], 20h ; ' '
0x1004bee9  mov     ebx, [ebp+arg_0]
0x1004beec  mov     byte ptr [ebp+var_4], 2
0x1004bef0  mov     [edi+4], ebx
0x1004bef3  mov     dword ptr [edi+8], 0
0x1004befa  mov     dword ptr [edi+14h], 0FFFFFFFFh
0x1004bf01  mov     dword ptr [edi+58h], 0
0x1004bf08  mov     eax, [ebx]
0x1004bf0a  mov     esi, [eax+3Ch]
0x1004bf0d  mov     ecx, esi
0x1004bf0f  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1004bf15  mov     ecx, ebx
0x1004bf17  call    esi
0x1004bf19  cmp     dword ptr [eax+18h], 0
0x1004bf1d  jle     short loc_1004BF33
0x1004bf1f  mov     ecx, [eax+5F4h]
0x1004bf25  cmp     ecx, 0FFFFFFFFh
0x1004bf28  jz      short loc_1004BF33
0x1004bf2a  mov     eax, [eax+ecx*4+574h]
0x1004bf31  jmp     short loc_1004BF35
0x1004bf33  xor     eax, eax
0x1004bf35  mov     eax, [eax+8]
0x1004bf38  push    5E4h; Size
0x1004bf3d  movzx   ebx, byte ptr [eax+40h]
0x1004bf41  and     ebx, 1
0x1004bf44  call    ??2@YAPAXI@Z; operator new(uint)
0x1004bf49  add     esp, 4
0x1004bf4c  mov     [ebp+Block], eax
0x1004bf4f  mov     ecx, eax; this
0x1004bf51  mov     byte ptr [ebp+var_4], 3
0x1004bf55  call    ??0Sort@@QAE@XZ; Sort::Sort(void)
0x1004bf5a  mov     byte ptr [ebp+var_4], 2
0x1004bf5e  mov     [edi+0Ch], eax
0x1004bf61  test    eax, eax
0x1004bf63  jnz     short loc_1004BFBE
0x1004bf65  mov     esi, [ebp+arg_4]
0x1004bf68  mov     eax, [esi]
0x1004bf6a  cmp     eax, 8
0x1004bf6d  jge     loc_1004BFF5
0x1004bf73  test    eax, 0FFFFFFFEh
0x1004bf78  jz      short loc_1004BF9A
0x1004bf7a  mov     eax, [esi+0Ch]
0x1004bf7d  test    eax, eax
0x1004bf7f  jz      short loc_1004BF8A
0x1004bf81  push    eax; Block
0x1004bf82  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1004bf87  add     esp, 4
0x1004bf8a  mov     eax, [esi+10h]
0x1004bf8d  test    eax, eax
0x1004bf8f  jz      short loc_1004BF9A
0x1004bf91  push    eax; Block
0x1004bf92  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1004bf97  add     esp, 4
0x1004bf9a  mov     dword ptr [esi], 8
0x1004bfa0  mov     dword ptr [esi+4], 0FFFFFC0Dh
0x1004bfa7  mov     dword ptr [esi+8], 0
0x1004bfae  mov     dword ptr [esi+0Ch], 0
0x1004bfb5  mov     dword ptr [esi+10h], 0
0x1004bfbc  jmp     short loc_1004BFF5
0x1004bfbe  mov     eax, [ebp+arg_0]
0x1004bfc1  mov     eax, [eax]
0x1004bfc3  mov     esi, [eax+38h]
0x1004bfc6  mov     ecx, esi
0x1004bfc8  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1004bfce  mov     ecx, [ebp+arg_0]
0x1004bfd1  call    esi
0x1004bfd3  push    [ebp+arg_4]
0x1004bfd6  mov     ecx, [edi+0Ch]
0x1004bfd9  push    40000h
0x1004bfde  push    ebx
0x1004bfdf  push    dword ptr [eax+0Ch]
0x1004bfe2  call    ?Open@Sort@@QAEXPAVSession@@W4SortMode@@KAAVErr@@@Z; Sort::Open(Session *,SortMode,ulong,Err &)
0x1004bfe7  mov     eax, [edi+0Ch]
0x1004bfea  inc     dword ptr [eax]
0x1004bfec  mov     eax, [edi+0Ch]
0x1004bfef  mov     eax, [eax+18h]
0x1004bff2  mov     [edi+10h], eax
0x1004bff5  mov     eax, edi
0x1004bff7  mov     ecx, [ebp+var_C]
0x1004bffa  mov     large fs:0, ecx
0x1004c001  pop     ecx
0x1004c002  pop     edi
0x1004c003  pop     esi
0x1004c004  pop     ebx
0x1004c005  mov     esp, ebp
0x1004c007  pop     ebp
0x1004c008  retn    8
0x10061670  mov     ecx, [ebp+var_10]; this
0x10061673  jmp     ??1Mover@@UAE@XZ; Mover::~Mover(void)
0x10061678  mov     ecx, [ebp+var_10]
0x1006167b  add     ecx, 28h ; '('; this
0x1006167e  jmp     ??1Key@@QAE@XZ; Key::~Key(void)
0x10061683  mov     ecx, [ebp+var_10]
0x10061686  add     ecx, 5Ch ; '\'; this
0x10061689  jmp     ??1Key@@QAE@XZ; Key::~Key(void)
0x1006168e  push    5E4h; unsigned int
0x10061693  mov     eax, [ebp+Block]
0x10061696  push    eax; Block
0x10061697  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x1006169c  add     esp, 8
0x1006169f  retn
0x100616a5  nop
0x100616a6  nop
0x100616a7  mov     edx, [esp-4+arg_4]
0x100616ab  lea     eax, [edx+0Ch]
0x100616ae  mov     ecx, [edx-18h]
0x100616b1  xor     ecx, eax; StackCookie
0x100616b3  call    @__security_check_cookie@4; __security_check_cookie(x)
0x100616b8  mov     eax, offset stru_10064024
0x100616bd  jmp     ___CxxFrameHandler3
```
