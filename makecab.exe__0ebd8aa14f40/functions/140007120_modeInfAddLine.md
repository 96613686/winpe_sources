# modeInfAddLine

- ea: `0x140007120`
- end: `0x1400072b4`
- name: `modeInfAddLine`
- size: `404`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1400054b0`

## callees

- `0x140007120`
- `0x140008620`
- `0x14000a29c`
- `0x14000a4f8`
- `0x14000c680`
- `0x14000dfd8`

## import_xrefs

- `msvcrt!atoi` at `0x14000714b`
- `msvcrt!atoi` at `0x14000714b`
- `msvcrt!malloc` at `0x1400071ef`
- `msvcrt!malloc` at `0x1400071ef`
- `msvcrt!free` at `0x140007251`
- `msvcrt!free` at `0x140007287`
- `msvcrt!free` at `0x140007251`
- `msvcrt!free` at `0x140007287`
- `msvcrt!_strdup` at `0x140007222`
- `msvcrt!_strdup` at `0x140007222`

## string_xrefs

- `0x140007164`: `Illegal to write to INF file area in layout section`

## pseudocode

```c
__int64 __fastcall modeInfAddLine(__int64 a1, unsigned int a2, const char *a3, __int64 a4)
{
  __int64 v8; // rax
  int v9; // eax
  const char *v10; // r8
  int v11; // ecx
  __int64 v13; // rsi
  __int64 v14; // rdx
  __int64 v15; // rax
  void *v16; // rbx
  char *v17; // rax

  v8 = VarFind(*(_QWORD *)(a1 + 16), "GenerateInf", a4);
  v9 = atoi(*(const char **)(v8 + 8));
  v11 = *(_DWORD *)(a1 + 192);
  if ( v11 == 3 && !v9 && a2 == 3 )
  {
    ErrSet(a4, "Illegal to write to INF file area in layout section", v10);
    return 0;
  }
  if ( !*(_DWORD *)(a1 + 32) )
    return 1;
  if ( v11 == 2 && a2 == 3 && *(int *)(a1 + 136) > 0 )
  {
    v13 = *(_QWORD *)(*(_QWORD *)(a1 + 184) + 8LL);
    if ( (*(_BYTE *)(v13 + 32) & 1) == 0 )
    {
      if ( !*(_QWORD *)(v13 + 56) )
      {
        v15 = GLCreateList(0, DestroyLineInfo, "INF file line", a4);
        *(_QWORD *)(v13 + 56) = v15;
        if ( !v15 )
          return 0;
      }
      v16 = malloc(0x10u);
      if ( !v16 )
      {
        ErrSet(a4, "Out of memory %1", "%s", "tracking INF file lines");
        return 0;
      }
      v17 = _strdup(a3);
      *((_QWORD *)v16 + 1) = v17;
      if ( v17 )
      {
        if ( GLAdd(*(char **)(v13 + 56), 0, (char *)v16, "INF file line", 0, a4) )
        {
          *(_DWORD *)v16 = 3;
          return 1;
        }
        free(*((void **)v16 + 1));
      }
      else
      {
        ErrSet(a4, "Out of memory %1", "%s", "tracking INF file lines");
      }
      free(v16);
      return 0;
    }
    v14 = 3;
  }
  else
  {
    v14 = a2;
  }
  return infAddLine(*(_QWORD *)(a1 + 144), v14, a3);
}

```

## disassembly

```asm
0x140007120  push    rbx
0x140007122  push    rbp
0x140007123  push    rsi
0x140007124  push    rdi
0x140007125  sub     rsp, 38h
0x140007129  mov     rbp, r8
0x14000712c  mov     esi, edx
0x14000712e  mov     rbx, rcx
0x140007131  lea     rdx, aGenerateinf; "GenerateInf"
0x140007138  mov     rcx, [rcx+10h]
0x14000713c  mov     r8, r9
0x14000713f  mov     rdi, r9
0x140007142  call    VarFind
0x140007147  mov     rcx, [rax+8]; String
0x14000714b  call    cs:__imp_atoi
0x140007151  mov     ecx, [rbx+0C0h]
0x140007157  cmp     ecx, 3
0x14000715a  jnz     short loc_14000717A
0x14000715c  test    eax, eax
0x14000715e  jnz     short loc_14000717A
0x140007160  cmp     esi, ecx
0x140007162  jnz     short loc_14000717A
0x140007164  lea     rdx, aIllegalToWrite; "Illegal to write to INF file area in la"...
0x14000716b  mov     rcx, rdi
0x14000716e  call    ErrSet
0x140007173  xor     eax, eax
0x140007175  jmp     loc_1400072AB
0x14000717a  cmp     dword ptr [rbx+20h], 0
0x14000717e  jnz     short loc_14000718A
0x140007180  mov     eax, 1
0x140007185  jmp     loc_1400072AB
0x14000718a  cmp     ecx, 2
0x14000718d  jnz     loc_14000729A
0x140007193  cmp     esi, 3
0x140007196  jnz     loc_14000729A
0x14000719c  cmp     dword ptr [rbx+88h], 0
0x1400071a3  jle     loc_14000729A
0x1400071a9  mov     rax, [rbx+0B8h]
0x1400071b0  mov     rsi, [rax+8]
0x1400071b4  test    byte ptr [rsi+20h], 1
0x1400071b8  jz      short loc_1400071C2
0x1400071ba  lea     edx, [rcx+1]
0x1400071bd  jmp     loc_14000729C
0x1400071c2  cmp     qword ptr [rsi+38h], 0
0x1400071c7  jnz     short loc_1400071EA
0x1400071c9  mov     r9, rdi
0x1400071cc  lea     r8, aInfFileLine; "INF file line"
0x1400071d3  lea     rdx, DestroyLineInfo
0x1400071da  xor     ecx, ecx
0x1400071dc  call    GLCreateList
0x1400071e1  mov     [rsi+38h], rax
0x1400071e5  test    rax, rax
0x1400071e8  jz      short loc_140007173
0x1400071ea  mov     ecx, 10h; Size
0x1400071ef  call    cs:__imp_malloc
0x1400071f5  mov     rbx, rax
0x1400071f8  test    rax, rax
0x1400071fb  jnz     short loc_14000721F
0x1400071fd  lea     r9, aTrackingInfFil; "tracking INF file lines"
0x140007204  mov     rcx, rdi
0x140007207  lea     r8, aS_4; "%s"
0x14000720e  lea     rdx, aOutOfMemory1; "Out of memory %1"
0x140007215  call    ErrSet
0x14000721a  jmp     loc_140007173
0x14000721f  mov     rcx, rbp; Source
0x140007222  call    cs:__imp__strdup
0x140007228  mov     [rbx+8], rax
0x14000722c  test    rax, rax
0x14000722f  jnz     short loc_14000725C
0x140007231  lea     r9, aTrackingInfFil; "tracking INF file lines"
0x140007238  mov     rcx, rdi
0x14000723b  lea     r8, aS_4; "%s"
0x140007242  lea     rdx, aOutOfMemory1; "Out of memory %1"
0x140007249  call    ErrSet
0x14000724e  mov     rcx, rbx; Block
0x140007251  call    cs:__imp_free
0x140007257  jmp     loc_140007173
0x14000725c  mov     rcx, [rsi+38h]
0x140007260  lea     r9, aInfFileLine; "INF file line"
0x140007267  mov     [rsp+58h+var_30], rdi
0x14000726c  mov     r8, rbx
0x14000726f  xor     edx, edx
0x140007271  mov     [rsp+58h+var_38], 0
0x140007279  call    GLAdd
0x14000727e  test    rax, rax
0x140007281  jnz     short loc_14000728F
0x140007283  mov     rcx, [rbx+8]; Block
0x140007287  call    cs:__imp_free
0x14000728d  jmp     short loc_14000724E
0x14000728f  mov     dword ptr [rbx], 3
0x140007295  jmp     loc_140007180
0x14000729a  mov     edx, esi
0x14000729c  mov     rcx, [rbx+90h]
0x1400072a3  mov     r8, rbp
0x1400072a6  call    infAddLine
0x1400072ab  add     rsp, 38h
0x1400072af  pop     rdi
0x1400072b0  pop     rsi
0x1400072b1  pop     rbp
0x1400072b2  pop     rbx
0x1400072b3  retn
```
