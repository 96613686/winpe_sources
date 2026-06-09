# CdpCompleteServerKernelConnectionQueue

- ea: `0x140008984`
- end: `0x140008a4e`
- name: `CdpCompleteServerKernelConnectionQueue`
- size: `202`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400083b0`
- `0x140008890`

## callees

- `0x140008984`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140008a25`
- `ntoskrnl!IofCompleteRequest` at `0x140008a25`

## pseudocode

```c
void __fastcall CdpCompleteServerKernelConnectionQueue(_QWORD *a1, int a2)
{
  _QWORD *v2; // rdi
  _QWORD *v4; // r8
  _QWORD *v6; // rbp
  _QWORD *v7; // r9
  _QWORD *v8; // rax
  _QWORD *v9; // rcx

  v2 = a1 + 30;
  v4 = (_QWORD *)a1[30];
  if ( v4 != a1 + 30 )
  {
    do
    {
      v6 = (_QWORD *)*v4;
      v7 = v4 - 21;
      if ( _InterlockedExchange64(v4 - 8, 0) )
      {
        v7[23] += 72LL;
        ++*((_BYTE *)v7 + 67);
        if ( a2 < 0 )
          --a1[32];
        else
          *(_QWORD *)(*(_QWORD *)(v7[23] + 48LL) + 24LL) = a1[28];
        v8 = (_QWORD *)*v4;
        if ( *(_QWORD **)(*v4 + 8LL) != v4 || (v9 = (_QWORD *)v4[1], (_QWORD *)*v9 != v4) )
          __fastfail(3u);
        *v9 = v8;
        v8[1] = v9;
        v4[1] = v4;
        *v4 = v4;
        *(_BYTE *)(v7[23] + 3LL) |= 1u;
        *((_DWORD *)v7 + 12) = a2;
        v7[7] = 0;
        IofCompleteRequest((PIRP)(v4 - 21), 0);
      }
      v4 = v6;
    }
    while ( v6 != v2 );
  }
}

```

## disassembly

```asm
0x140008984  push    rbx
0x140008986  push    rbp
0x140008987  push    rsi
0x140008988  push    rdi
0x140008989  sub     rsp, 28h
0x14000898d  lea     rdi, [rcx+0F0h]
0x140008994  mov     esi, edx
0x140008996  mov     r8, [rdi]
0x140008999  mov     rbx, rcx
0x14000899c  cmp     r8, rdi
0x14000899f  jz      loc_140008A3D
0x1400089a5  mov     rbp, [r8]
0x1400089a8  lea     r9, [r8-0A8h]
0x1400089af  xor     eax, eax
0x1400089b1  xchg    rax, [r9+68h]
0x1400089b5  test    rax, rax
0x1400089b8  jz      short loc_140008A31
0x1400089ba  add     qword ptr [r9+0B8h], 48h ; 'H'
0x1400089c2  inc     byte ptr [r9+43h]
0x1400089c6  mov     rcx, [r9+0B8h]
0x1400089cd  test    esi, esi
0x1400089cf  js      short loc_1400089E2
0x1400089d1  mov     rcx, [rcx+30h]
0x1400089d5  mov     rax, [rbx+0E0h]
0x1400089dc  mov     [rcx+18h], rax
0x1400089e0  jmp     short loc_1400089E9
0x1400089e2  dec     qword ptr [rbx+100h]
0x1400089e9  mov     rax, [r8]
0x1400089ec  cmp     [rax+8], r8
0x1400089f0  jnz     short loc_140008A47
0x1400089f2  mov     rcx, [r8+8]
0x1400089f6  cmp     [rcx], r8
0x1400089f9  jnz     short loc_140008A47
0x1400089fb  mov     [rcx], rax
0x1400089fe  xor     edx, edx; PriorityBoost
0x140008a00  mov     [rax+8], rcx
0x140008a04  mov     rcx, r9; Irp
0x140008a07  mov     [r8+8], r8
0x140008a0b  mov     [r8], r8
0x140008a0e  mov     rax, [r9+0B8h]
0x140008a15  or      byte ptr [rax+3], 1
0x140008a19  mov     [r9+30h], esi
0x140008a1d  mov     qword ptr [r9+38h], 0
0x140008a25  call    cs:__imp_IofCompleteRequest
0x140008a2c  nop     dword ptr [rax+rax+00h]
0x140008a31  mov     r8, rbp
0x140008a34  cmp     rbp, rdi
0x140008a37  jnz     loc_1400089A5
0x140008a3d  add     rsp, 28h
0x140008a41  pop     rdi
0x140008a42  pop     rsi
0x140008a43  pop     rbp
0x140008a44  pop     rbx
0x140008a45  retn
0x140008a47  mov     ecx, 3
0x140008a4c  int     29h; Win8: RtlFailFast(ecx)
```
