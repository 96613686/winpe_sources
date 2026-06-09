# CSettableProperties::~CSettableProperties(void)

- ea: `0x10020410`
- end: `0x100204ac`
- name: `??1CSettableProperties@@UAE@XZ`
- size: `156`
- prototype: `void __thiscall(CSettableProperties *__hidden this)`
- caller_count: `26`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1000e140`
- `0x1000e8d0`
- `0x10013d50`
- `0x10013f50`
- `0x100153e0`
- `0x10015d90`
- `0x10015dc0`
- `0x10017960`
- `0x1001a970`
- `0x1001af60`
- `0x1001b4a0`
- `0x1001d7f0`
- `0x1001e350`
- `0x1001ebc0`
- `0x10025180`
- `0x10027f00`
- `0x1002e3e0`
- `0x10034e00`
- `0x100407e0`
- `0x10040c30`
- `0x10040ed0`
- `0x10044ee0`
- `0x10045d20`
- `0x100467c0`
- `0x10046bb0`
- `0x10047070`

## callees

- `0x1001c6d0`
- `0x10020410`
- `0x1004cea1`

## pseudocode

```c
void __thiscall CSettableProperties::~CSettableProperties(CSettableProperties *this)
{
  int v1; // edi
  int v2; // eax
  _DWORD *v3; // esi
  void (__thiscall ***v4)(_DWORD, int); // ebx
  bool v5; // zf
  CSettableProperties *v6; // [esp+Ch] [ebp-Ch]
  int v7; // [esp+10h] [ebp-8h]
  int v8; // [esp+14h] [ebp-4h]

  v1 = 2;
  v6 = this;
  v2 = 2;
  *(_DWORD *)this = &CSettableProperties::`vftable';
  v8 = 2;
  v7 = 2;
  do
  {
    v3 = (_DWORD *)*((_DWORD *)this + v1);
    if ( v3 )
    {
      v4 = (void (__thiscall ***)(_DWORD, int))v3[4];
      *v3 = &JoltProperties::`vftable';
      if ( v4 )
      {
        if ( *(v4 - 1) )
        {
          (**v4)(v4, 3);
          v1 = v8;
        }
        else
        {
          operator delete(v4 - 1);
        }
      }
      v3[4] = 0;
      v3[2] = 0;
      v3[3] = 0;
      operator delete(v3);
      this = v6;
      v2 = v7;
      *((_DWORD *)v6 + v1) = 0;
    }
    ++v1;
    v5 = v2-- == 1;
    v8 = v1;
    v7 = v2;
  }
  while ( !v5 );
}

```

## disassembly

```asm
0x10020410  mov     edi, edi
0x10020412  push    ebp
0x10020413  mov     ebp, esp
0x10020415  sub     esp, 0Ch
0x10020418  push    ebx
0x10020419  push    esi
0x1002041a  push    edi
0x1002041b  mov     edi, 2
0x10020420  mov     [ebp+var_C], ecx
0x10020423  mov     eax, edi
0x10020425  mov     dword ptr [ecx], offset ??_7CSettableProperties@@6B@; const CSettableProperties::`vftable'
0x1002042b  mov     [ebp+var_4], edi
0x1002042e  mov     [ebp+var_8], eax
0x10020431  mov     esi, [ecx+edi*4]
0x10020434  test    esi, esi
0x10020436  jz      short loc_10020499
0x10020438  mov     ebx, [esi+10h]
0x1002043b  mov     dword ptr [esi], offset ??_7JoltProperties@@6B@; const JoltProperties::`vftable'
0x10020441  test    ebx, ebx
0x10020443  jz      short loc_1002046E
0x10020445  cmp     dword ptr [ebx-4], 0
0x10020449  lea     eax, [ebx-4]
0x1002044c  jz      short loc_10020465
0x1002044e  mov     eax, [ebx]
0x10020450  push    3
0x10020452  mov     edi, [eax]
0x10020454  mov     ecx, edi
0x10020456  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1002045c  mov     ecx, ebx
0x1002045e  call    edi
0x10020460  mov     edi, [ebp+var_4]
0x10020463  jmp     short loc_1002046E
0x10020465  push    eax; Block
0x10020466  call    ??3@YAXPAX@Z; operator delete(void *)
0x1002046b  add     esp, 4
0x1002046e  push    esi; Block
0x1002046f  mov     dword ptr [esi+10h], 0
0x10020476  mov     dword ptr [esi+8], 0
0x1002047d  mov     dword ptr [esi+0Ch], 0
0x10020484  call    ??3@YAXPAX@Z; operator delete(void *)
0x10020489  mov     ecx, [ebp+var_C]
0x1002048c  add     esp, 4
0x1002048f  mov     eax, [ebp+var_8]
0x10020492  mov     dword ptr [ecx+edi*4], 0
0x10020499  inc     edi
0x1002049a  add     eax, 0FFFFFFFFh
0x1002049d  mov     [ebp+var_4], edi
0x100204a0  mov     [ebp+var_8], eax
0x100204a3  jnz     short loc_10020431
0x100204a5  pop     edi
0x100204a6  pop     esi
0x100204a7  pop     ebx
0x100204a8  mov     esp, ebp
0x100204aa  pop     ebp
0x100204ab  retn
```
