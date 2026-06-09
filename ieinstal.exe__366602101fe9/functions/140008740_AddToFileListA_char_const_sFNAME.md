# AddToFileListA(char const *,sFNAME * *)

- ea: `0x140008740`
- end: `0x1400088a2`
- name: `?AddToFileListA@@YAJPEBDPEAPEAUsFNAME@@@Z`
- size: `354`
- prototype: `__int64 __fastcall(const char *, struct sFNAME **)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x140008684`
- `0x1400088a8`

## callees

- `0x140008740`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x1400087a3`
- `ole32!CoTaskMemAlloc` at `0x1400087cc`
- `ole32!CoTaskMemAlloc` at `0x1400087a3`
- `ole32!CoTaskMemAlloc` at `0x1400087cc`
- `ole32!CoTaskMemFree` at `0x140008861`
- `ole32!CoTaskMemFree` at `0x140008877`
- `ole32!CoTaskMemFree` at `0x140008861`
- `ole32!CoTaskMemFree` at `0x140008877`

## pseudocode

```c
__int64 __fastcall AddToFileListA(const char *a1, struct sFNAME **a2)
{
  const char *v3; // r14
  const char *v4; // rax
  __int64 v5; // r8
  unsigned int v6; // ebx
  unsigned int v7; // ecx
  __int64 v8; // rsi
  _QWORD *v9; // rdi
  unsigned __int64 v10; // rsi
  _BYTE *v11; // rax
  _BYTE *v12; // rcx
  __int64 v13; // rax
  _BYTE *v14; // rcx

  v3 = a1;
  if ( !a1 )
    return (unsigned int)-2147024809;
  v4 = a1;
  v5 = 260;
  do
  {
    if ( !*v4 )
      break;
    ++v4;
    --v5;
  }
  while ( v5 );
  v6 = -2147024809;
  v7 = v5 == 0 ? 0x80070057 : 0;
  v8 = (260 - v5) & -(__int64)(v5 != 0);
  if ( !v5 )
    return v7;
  v9 = CoTaskMemAlloc(0x18u);
  if ( !v9 )
    return (unsigned int)-2147024882;
  *(_OWORD *)v9 = 0;
  v10 = v8 + 1;
  v9[2] = 0;
  v11 = CoTaskMemAlloc((unsigned int)v10);
  *v9 = v11;
  v12 = v11;
  if ( !v11 )
  {
    v6 = -2147024882;
    goto LABEL_30;
  }
  if ( v10 )
  {
    if ( v10 <= 0x7FFFFFFF )
    {
      v13 = 2147483646;
      do
      {
        if ( !v13 )
          break;
        if ( !*v3 )
          break;
        *v12++ = *v3++;
        --v13;
        --v10;
      }
      while ( v10 );
      v11 = v12 - 1;
      if ( v10 )
        v11 = v12;
      v6 = v10 == 0 ? 0x8007007A : 0;
    }
    *v11 = 0;
  }
  v14 = (_BYTE *)*v9;
  if ( (v6 & 0x80000000) != 0 )
  {
    CoTaskMemFree(v14);
LABEL_30:
    CoTaskMemFree(v9);
    return v6;
  }
  if ( v14 )
  {
    while ( *v14 )
    {
      if ( *v14 == 47 )
        *v14 = 92;
      ++v14;
    }
  }
  if ( *a2 )
    v9[1] = *a2;
  *a2 = (struct sFNAME *)v9;
  return v6;
}

```

## disassembly

```asm
0x140008740  push    rbx
0x140008742  push    rsi
0x140008743  push    rdi
0x140008744  push    r14
0x140008746  push    r15
0x140008748  sub     rsp, 20h
0x14000874c  mov     r15, rdx
0x14000874f  mov     r14, rcx
0x140008752  test    rcx, rcx
0x140008755  jz      loc_14000888C
0x14000875b  mov     r9d, 104h
0x140008761  mov     rax, rcx
0x140008764  mov     r8d, r9d
0x140008767  cmp     byte ptr [rax], 0
0x14000876a  jz      short loc_140008775
0x14000876c  inc     rax
0x14000876f  sub     r8, 1
0x140008773  jnz     short loc_140008767
0x140008775  mov     rax, r8
0x140008778  mov     ebx, 80070057h
0x14000877d  neg     rax
0x140008780  mov     rax, r8
0x140008783  sbb     ecx, ecx
0x140008785  sub     r9, r8
0x140008788  not     ecx
0x14000878a  and     ecx, ebx
0x14000878c  neg     rax
0x14000878f  sbb     rsi, rsi
0x140008792  and     rsi, r9
0x140008795  test    r8, r8
0x140008798  jz      loc_140008891
0x14000879e  mov     ecx, 18h; cb
0x1400087a3  call    cs:__imp_CoTaskMemAlloc
0x1400087aa  nop     dword ptr [rax+rax+00h]
0x1400087af  mov     rdi, rax
0x1400087b2  test    rax, rax
0x1400087b5  jz      loc_140008885
0x1400087bb  xorps   xmm0, xmm0
0x1400087be  xor     eax, eax
0x1400087c0  movups  xmmword ptr [rdi], xmm0
0x1400087c3  inc     rsi
0x1400087c6  mov     [rdi+10h], rax
0x1400087ca  mov     ecx, esi; cb
0x1400087cc  call    cs:__imp_CoTaskMemAlloc
0x1400087d3  nop     dword ptr [rax+rax+00h]
0x1400087d8  mov     [rdi], rax
0x1400087db  mov     rcx, rax
0x1400087de  test    rax, rax
0x1400087e1  jz      loc_14000886F
0x1400087e7  test    rsi, rsi
0x1400087ea  jz      short loc_140008832
0x1400087ec  cmp     rsi, 7FFFFFFFh
0x1400087f3  ja      short loc_14000882F
0x1400087f5  mov     eax, 7FFFFFFEh
0x1400087fa  test    rax, rax
0x1400087fd  jz      short loc_140008817
0x1400087ff  mov     dl, [r14]
0x140008802  test    dl, dl
0x140008804  jz      short loc_140008817
0x140008806  mov     [rcx], dl
0x140008808  inc     r14
0x14000880b  inc     rcx
0x14000880e  dec     rax
0x140008811  sub     rsi, 1
0x140008815  jnz     short loc_1400087FA
0x140008817  test    rsi, rsi
0x14000881a  lea     rax, [rcx-1]
0x14000881e  cmovnz  rax, rcx
0x140008822  neg     rsi
0x140008825  sbb     ebx, ebx
0x140008827  not     ebx
0x140008829  and     ebx, 8007007Ah
0x14000882f  mov     byte ptr [rax], 0
0x140008832  mov     rcx, [rdi]; pv
0x140008835  test    ebx, ebx
0x140008837  js      short loc_140008861
0x140008839  test    rcx, rcx
0x14000883c  jz      short loc_140008850
0x14000883e  jmp     short loc_14000884A
0x140008840  cmp     al, 2Fh ; '/'
0x140008842  jnz     short loc_140008847
0x140008844  mov     byte ptr [rcx], 5Ch ; '\'
0x140008847  inc     rcx
0x14000884a  mov     al, [rcx]
0x14000884c  test    al, al
0x14000884e  jnz     short loc_140008840
0x140008850  mov     rax, [r15]
0x140008853  test    rax, rax
0x140008856  jz      short loc_14000885C
0x140008858  mov     [rdi+8], rax
0x14000885c  mov     [r15], rdi
0x14000885f  jmp     short loc_140008893
0x140008861  call    cs:__imp_CoTaskMemFree
0x140008868  nop     dword ptr [rax+rax+00h]
0x14000886d  jmp     short loc_140008874
0x14000886f  mov     ebx, 8007000Eh
0x140008874  mov     rcx, rdi; pv
0x140008877  call    cs:__imp_CoTaskMemFree
0x14000887e  nop     dword ptr [rax+rax+00h]
0x140008883  jmp     short loc_140008893
0x140008885  mov     ebx, 8007000Eh
0x14000888a  jmp     short loc_140008893
0x14000888c  mov     ecx, 80070057h
0x140008891  mov     ebx, ecx
0x140008893  mov     eax, ebx
0x140008895  add     rsp, 20h
0x140008899  pop     r15
0x14000889b  pop     r14
0x14000889d  pop     rdi
0x14000889e  pop     rsi
0x14000889f  pop     rbx
0x1400088a0  retn
```
