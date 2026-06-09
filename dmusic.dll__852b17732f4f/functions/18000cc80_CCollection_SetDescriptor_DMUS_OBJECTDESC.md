# CCollection::SetDescriptor(_DMUS_OBJECTDESC *)

- ea: `0x18000cc80`
- end: `0x18000cd88`
- name: `?SetDescriptor@CCollection@@UEAAJPEAU_DMUS_OBJECTDESC@@@Z`
- size: `264`
- prototype: `__int64 __fastcall(CCollection *__hidden this, struct _DMUS_OBJECTDESC *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000cc80`

## pseudocode

```c
__int64 __fastcall CCollection::SetDescriptor(CCollection *this, struct _DMUS_OBJECTDESC *a2)
{
  int v4; // r11d
  int v5; // eax
  __int64 v6; // rcx
  _WORD *v7; // r9
  __int64 v8; // r8
  _WORD *v9; // rax
  _WORD *v10; // rcx
  int v11; // ecx

  if ( !a2 )
    return 2147500035LL;
  if ( (unsigned int)(*(_DWORD *)a2 - 1) <= 0x356 )
    return 2147942487LL;
  v4 = *((_DWORD *)a2 + 1);
  if ( !v4 )
    return 0;
  if ( (v4 & 1) != 0 )
    *((_OWORD *)this + 13) = *(_OWORD *)((char *)a2 + 8);
  v5 = *((_DWORD *)a2 + 1);
  if ( (v5 & 2) != 0 )
  {
    v5 &= ~2u;
    *((_DWORD *)a2 + 1) = v5;
  }
  if ( (v5 & 4) != 0 )
  {
    v6 = 2147483646;
    v7 = (_WORD *)((char *)a2 + 56);
    v8 = 64;
    v9 = (_WORD *)((char *)this + 72);
    do
    {
      if ( !v6 )
        break;
      if ( !*v7 )
        break;
      *v9++ = *v7++;
      --v6;
      --v8;
    }
    while ( v8 );
    v10 = v9 - 1;
    if ( v8 )
      v10 = v9;
    *v10 = 0;
  }
  v11 = *((_DWORD *)a2 + 1);
  if ( (v11 & 8) != 0 )
  {
    v11 &= ~8u;
    *((_DWORD *)a2 + 1) = v11;
  }
  if ( (v11 & 0x10) != 0 )
  {
    v11 &= ~0x10u;
    *((_DWORD *)a2 + 1) = v11;
  }
  if ( (v11 & 0x20) != 0 )
  {
    v11 &= ~0x20u;
    *((_DWORD *)a2 + 1) = v11;
  }
  if ( (v11 & 0x40) != 0 )
  {
    v11 &= ~0x40u;
    *((_DWORD *)a2 + 1) = v11;
  }
  if ( (v11 & 0x80u) != 0 )
  {
    v11 &= ~0x80u;
    *((_DWORD *)a2 + 1) = v11;
  }
  if ( (v11 & 0x100) != 0 )
  {
    v11 &= ~0x100u;
    *((_DWORD *)a2 + 1) = v11;
  }
  if ( (v11 & 0x200) != 0 )
  {
    v11 &= ~0x200u;
    *((_DWORD *)a2 + 1) = v11;
  }
  return v4 != v11;
}

```

## disassembly

```asm
0x18000cc80  mov     [rsp+arg_0], rbx
0x18000cc85  xor     ebx, ebx
0x18000cc87  mov     r10, rcx
0x18000cc8a  test    rdx, rdx
0x18000cc8d  jnz     short loc_18000CC99
0x18000cc8f  mov     eax, 80004003h
0x18000cc94  jmp     loc_18000CD82
0x18000cc99  mov     eax, [rdx]
0x18000cc9b  dec     eax
0x18000cc9d  cmp     eax, 356h
0x18000cca2  ja      short loc_18000CCAE
0x18000cca4  mov     eax, 80070057h
0x18000cca9  jmp     loc_18000CD82
0x18000ccae  mov     r11d, [rdx+4]
0x18000ccb2  test    r11d, r11d
0x18000ccb5  jnz     short loc_18000CCBE
0x18000ccb7  xor     eax, eax
0x18000ccb9  jmp     loc_18000CD82
0x18000ccbe  test    r11b, 1
0x18000ccc2  jz      short loc_18000CCD0
0x18000ccc4  movups  xmm0, xmmword ptr [rdx+8]
0x18000ccc8  movdqu  xmmword ptr [rcx+0D0h], xmm0
0x18000ccd0  mov     eax, [rdx+4]
0x18000ccd3  test    al, 2
0x18000ccd5  jz      short loc_18000CCDD
0x18000ccd7  and     eax, 0FFFFFFFDh
0x18000ccda  mov     [rdx+4], eax
0x18000ccdd  test    al, 4
0x18000ccdf  jz      short loc_18000CD26
0x18000cce1  mov     ecx, 7FFFFFFEh
0x18000cce6  lea     r9, [rdx+38h]
0x18000ccea  mov     r8d, 40h ; '@'
0x18000ccf0  lea     rax, [r10+48h]
0x18000ccf4  test    rcx, rcx
0x18000ccf7  jz      short loc_18000CD18
0x18000ccf9  movzx   r10d, word ptr [r9]
0x18000ccfd  test    r10w, r10w
0x18000cd01  jz      short loc_18000CD18
0x18000cd03  mov     [rax], r10w
0x18000cd07  add     r9, 2
0x18000cd0b  add     rax, 2
0x18000cd0f  dec     rcx
0x18000cd12  sub     r8, 1
0x18000cd16  jnz     short loc_18000CCF4
0x18000cd18  test    r8, r8
0x18000cd1b  lea     rcx, [rax-2]
0x18000cd1f  cmovnz  rcx, rax
0x18000cd23  mov     [rcx], bx
0x18000cd26  mov     ecx, [rdx+4]
0x18000cd29  test    cl, 8
0x18000cd2c  jz      short loc_18000CD34
0x18000cd2e  and     ecx, 0FFFFFFF7h
0x18000cd31  mov     [rdx+4], ecx
0x18000cd34  test    cl, 10h
0x18000cd37  jz      short loc_18000CD3F
0x18000cd39  and     ecx, 0FFFFFFEFh
0x18000cd3c  mov     [rdx+4], ecx
0x18000cd3f  test    cl, 20h
0x18000cd42  jz      short loc_18000CD4A
0x18000cd44  and     ecx, 0FFFFFFDFh
0x18000cd47  mov     [rdx+4], ecx
0x18000cd4a  test    cl, 40h
0x18000cd4d  jz      short loc_18000CD55
0x18000cd4f  and     ecx, 0FFFFFFBFh
0x18000cd52  mov     [rdx+4], ecx
0x18000cd55  test    cl, cl
0x18000cd57  jns     short loc_18000CD60
0x18000cd59  btr     ecx, 7
0x18000cd5d  mov     [rdx+4], ecx
0x18000cd60  bt      ecx, 8
0x18000cd64  jnb     short loc_18000CD6D
0x18000cd66  btr     ecx, 8
0x18000cd6a  mov     [rdx+4], ecx
0x18000cd6d  bt      ecx, 9
0x18000cd71  jnb     short loc_18000CD7A
0x18000cd73  btr     ecx, 9
0x18000cd77  mov     [rdx+4], ecx
0x18000cd7a  cmp     r11d, ecx
0x18000cd7d  mov     eax, ebx
0x18000cd7f  setnz   al
0x18000cd82  mov     rbx, [rsp+arg_0]
0x18000cd87  retn
```
