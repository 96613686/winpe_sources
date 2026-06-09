# MBR_ENTRY::ComputeChs(_DISK_GEOMETRY *)

- ea: `0x14000fb14`
- end: `0x14000fbce`
- name: `?ComputeChs@MBR_ENTRY@@QEAAXPEAU_DISK_GEOMETRY@@@Z`
- size: `186`
- prototype: `void __fastcall(MBR_ENTRY *__hidden this, struct _DISK_GEOMETRY *)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000fc84`
- `0x140010380`

## callees

- `0x14000fb14`

## pseudocode

```c
void __fastcall MBR_ENTRY::ComputeChs(MBR_ENTRY *this, struct _DISK_GEOMETRY *a2)
{
  DWORD v2; // esi
  char *v4; // rax
  int v5; // ecx
  DWORD v6; // edi
  __int64 v7; // rbx
  DWORD v8; // eax
  DWORD v9; // ecx
  unsigned int v10; // r10d
  unsigned int v11; // r11d
  DWORD SectorsPerTrack; // r8d
  _BYTE *v13; // rdx
  _QWORD v14[3]; // [rsp+0h] [rbp-18h]
  int v15; // [rsp+20h] [rbp+8h]
  int v16; // [rsp+24h] [rbp+Ch]

  v2 = a2->SectorsPerTrack * a2->TracksPerCylinder;
  v14[0] = (char *)this + 1;
  v4 = (char *)this + 5;
  v15 = *((_DWORD *)this + 2);
  v5 = *((_DWORD *)this + 3) + v15 - 1;
  v14[1] = v4;
  v6 = a2->Cylinders.LowPart * v2;
  v7 = 0;
  v16 = v5;
  do
  {
    v8 = *(&v15 + v7);
    if ( v8 >= v6 )
    {
      v10 = a2->Cylinders.LowPart - 1;
      SectorsPerTrack = a2->SectorsPerTrack;
      LOBYTE(v11) = a2->TracksPerCylinder - 1;
    }
    else
    {
      v9 = a2->SectorsPerTrack;
      v10 = v8 / v2;
      v11 = v8 % v2 / v9;
      LOBYTE(SectorsPerTrack) = v8 % v2 % v9 + 1;
    }
    v13 = (_BYTE *)v14[v7++];
    *v13 = v11;
    v13[1] = (v10 >> 2) ^ (SectorsPerTrack ^ (v10 >> 2)) & 0x3F;
    v13[2] = v10;
  }
  while ( v7 != 2 );
}

```

## disassembly

```asm
0x14000fb14  mov     [rsp+arg_8], rbx
0x14000fb19  mov     [rsp+arg_10], rsi
0x14000fb1e  push    rdi
0x14000fb1f  sub     rsp, 10h
0x14000fb23  mov     esi, [rdx+0Ch]
0x14000fb26  lea     rax, [rcx+1]
0x14000fb2a  imul    esi, [rdx+10h]
0x14000fb2e  mov     r8, rcx
0x14000fb31  mov     [rsp+18h+var_18], rax
0x14000fb35  mov     r9, rdx
0x14000fb38  lea     rax, [rcx+5]
0x14000fb3c  mov     ecx, [rcx+8]
0x14000fb3f  mov     [rsp+18h+arg_0], ecx
0x14000fb43  dec     ecx
0x14000fb45  add     ecx, [r8+0Ch]
0x14000fb49  mov     edi, esi
0x14000fb4b  mov     [rsp+18h+var_10], rax
0x14000fb50  imul    edi, [rdx]
0x14000fb53  xor     ebx, ebx
0x14000fb55  mov     [rsp+18h+arg_4], ecx
0x14000fb59  mov     eax, [rsp+rbx*4+18h+arg_0]
0x14000fb5d  cmp     eax, edi
0x14000fb5f  jnb     short loc_14000FB86
0x14000fb61  mov     ecx, [r9+10h]
0x14000fb65  xor     edx, edx
0x14000fb67  div     esi
0x14000fb69  mov     r8d, edx
0x14000fb6c  mov     r10d, eax
0x14000fb6f  xor     edx, edx
0x14000fb71  mov     eax, r8d
0x14000fb74  div     ecx
0x14000fb76  xor     edx, edx
0x14000fb78  mov     r11d, eax
0x14000fb7b  mov     eax, r8d
0x14000fb7e  div     ecx
0x14000fb80  lea     r8d, [rdx+1]
0x14000fb84  jmp     short loc_14000FB97
0x14000fb86  mov     r10d, [r9]
0x14000fb89  mov     r11d, [r9+0Ch]
0x14000fb8d  dec     r10d
0x14000fb90  mov     r8d, [r9+10h]
0x14000fb94  dec     r11d
0x14000fb97  mov     rdx, [rsp+rbx*8+18h+var_18]
0x14000fb9b  mov     ecx, r10d
0x14000fb9e  shr     ecx, 2
0x14000fba1  inc     rbx
0x14000fba4  mov     al, cl
0x14000fba6  xor     al, r8b
0x14000fba9  and     al, 3Fh
0x14000fbab  mov     [rdx], r11b
0x14000fbae  xor     al, cl
0x14000fbb0  mov     [rdx+1], al
0x14000fbb3  mov     [rdx+2], r10b
0x14000fbb7  cmp     rbx, 2
0x14000fbbb  jnz     short loc_14000FB59
0x14000fbbd  mov     rbx, [rsp+18h+arg_8]
0x14000fbc2  mov     rsi, [rsp+18h+arg_10]
0x14000fbc7  add     rsp, 10h
0x14000fbcb  pop     rdi
0x14000fbcc  retn
```
