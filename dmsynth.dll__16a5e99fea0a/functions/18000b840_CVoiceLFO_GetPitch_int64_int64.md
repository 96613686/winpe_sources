# CVoiceLFO::GetPitch(__int64,__int64 *)

- ea: `0x18000b840`
- end: `0x18000b937`
- name: `?GetPitch@CVoiceLFO@@QEAAJ_JPEA_J@Z`
- size: `247`
- prototype: `__int64 __fastcall(CVoiceLFO *__hidden this, __int64, __int64 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b710`
- `0x18000c710`

## callees

- `0x18000b840`

## pseudocode

```c
__int64 __fastcall CVoiceLFO::GetPitch(CVoiceLFO *this, __int64 a2, __int64 *a3)
{
  __int64 **v7; // rcx
  __int64 *v8; // rax
  int i; // edx
  __int64 **v10; // rax
  __int64 *v11; // rcx
  int j; // r8d
  int v13; // edx
  __int64 v14; // r9
  int v15; // eax
  unsigned int v16; // edx

  if ( !*((_DWORD *)this + 18) )
    return 0;
  v7 = (__int64 **)*((_QWORD *)this + 8);
  v8 = *v7;
  for ( i = *((_DWORD *)v7 + 4); v8; v8 = (__int64 *)*v8 )
  {
    if ( v8[1] > a2 )
      break;
    i = *((_DWORD *)v8 + 4);
  }
  v10 = (__int64 **)*((_QWORD *)this + 6);
  v11 = *v10;
  for ( j = *((_DWORD *)v10 + 4); v11; v11 = (__int64 *)*v11 )
  {
    if ( v11[1] > a2 )
      break;
    j = *((_DWORD *)v11 + 4);
  }
  v13 = *((__int16 *)this + 11) + i * *((__int16 *)this + 12) / 127 + j * *((__int16 *)this + 9) / 127;
  v14 = a2 - *((_QWORD *)this + 5) - *((_QWORD *)this + 1);
  if ( v14 >= 0 )
  {
    *a3 = *((_QWORD *)this + 7);
    v15 = *((__int16 *)&CVoiceLFO::m_snSineTable + (unsigned __int8)((unsigned int)(v14 * *(_DWORD *)this) >> 16));
  }
  else
  {
    *a3 = -v14;
    v15 = 0;
  }
  v16 = (int)((unsigned __int64)(1374389535LL * v15 * v13) >> 32) >> 5;
  return v16 + (v16 >> 31);
}

```

## disassembly

```asm
0x18000b840  mov     [rsp+arg_0], rbx
0x18000b845  cmp     dword ptr [rcx+48h], 0
0x18000b849  mov     rbx, r8
0x18000b84c  mov     r9, rdx
0x18000b84f  mov     r10, rcx
0x18000b852  jnz     short loc_18000B85C
0x18000b854  xor     eax, eax
0x18000b856  mov     rbx, [rsp+arg_0]
0x18000b85b  retn
0x18000b85c  mov     rcx, [rcx+40h]
0x18000b860  mov     rax, [rcx]
0x18000b863  mov     edx, [rcx+10h]
0x18000b866  test    rax, rax
0x18000b869  jz      short loc_18000B881
0x18000b86b  nop     dword ptr [rax+rax+00h]
0x18000b870  cmp     [rax+8], r9
0x18000b874  jg      short loc_18000B881
0x18000b876  mov     edx, [rax+10h]
0x18000b879  mov     rax, [rax]
0x18000b87c  test    rax, rax
0x18000b87f  jnz     short loc_18000B870
0x18000b881  movsx   ecx, word ptr [r10+18h]
0x18000b886  mov     eax, 81020409h
0x18000b88b  imul    ecx, edx
0x18000b88e  imul    ecx
0x18000b890  lea     r11d, [rcx+rdx]
0x18000b894  sar     r11d, 6
0x18000b898  mov     eax, r11d
0x18000b89b  shr     eax, 1Fh
0x18000b89e  add     r11d, eax
0x18000b8a1  mov     rax, [r10+30h]
0x18000b8a5  mov     rcx, [rax]
0x18000b8a8  mov     r8d, [rax+10h]
0x18000b8ac  test    rcx, rcx
0x18000b8af  jz      short loc_18000B8C3
0x18000b8b1  cmp     [rcx+8], r9
0x18000b8b5  jg      short loc_18000B8C3
0x18000b8b7  mov     r8d, [rcx+10h]
0x18000b8bb  mov     rcx, [rcx]
0x18000b8be  test    rcx, rcx
0x18000b8c1  jnz     short loc_18000B8B1
0x18000b8c3  movsx   ecx, word ptr [r10+12h]
0x18000b8c8  mov     eax, 81020409h
0x18000b8cd  sub     r9, [r10+28h]
0x18000b8d1  imul    ecx, r8d
0x18000b8d5  imul    ecx
0x18000b8d7  add     edx, ecx
0x18000b8d9  movsx   ecx, word ptr [r10+16h]
0x18000b8de  sar     edx, 6
0x18000b8e1  mov     eax, edx
0x18000b8e3  shr     eax, 1Fh
0x18000b8e6  add     edx, eax
0x18000b8e8  add     edx, r11d
0x18000b8eb  add     edx, ecx
0x18000b8ed  sub     r9, [r10+8]
0x18000b8f1  jns     short loc_18000B8FD
0x18000b8f3  neg     r9
0x18000b8f6  mov     [rbx], r9
0x18000b8f9  xor     eax, eax
0x18000b8fb  jmp     short loc_18000B91D
0x18000b8fd  mov     rax, [r10+38h]
0x18000b901  lea     rcx, ?m_snSineTable@CVoiceLFO@@0PAFA; short near * CVoiceLFO::m_snSineTable
0x18000b908  mov     [rbx], rax
0x18000b90b  mov     eax, [r10]
0x18000b90e  imul    rax, r9
0x18000b912  sar     rax, 10h
0x18000b916  movzx   eax, al
0x18000b919  movsx   eax, word ptr [rcx+rax*2]
0x18000b91d  mov     rbx, [rsp+arg_0]
0x18000b922  imul    edx, eax
0x18000b925  mov     eax, 51EB851Fh
0x18000b92a  imul    edx
0x18000b92c  sar     edx, 5
0x18000b92f  mov     eax, edx
0x18000b931  shr     eax, 1Fh
0x18000b934  add     eax, edx
0x18000b936  retn
```
