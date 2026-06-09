# PROTOCOL::Send(_LIST_ENTRY *,int)

- ea: `0x1800039a0`
- end: `0x180003acc`
- name: `?Send@PROTOCOL@@UEAAJPEAU_LIST_ENTRY@@H@Z`
- size: `300`
- prototype: `__int64 __fastcall(PROTOCOL *__hidden this, struct _LIST_ENTRY *, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180002f60`
- `0x1800030dc`
- `0x1800039a0`
- `0x180009128`

## pseudocode

```c
__int64 __fastcall PROTOCOL::Send(PROTOCOL *this, struct _LIST_ENTRY *a2)
{
  struct _LIST_ENTRY *Flink; // r10
  struct _LIST_ENTRY *v3; // rax
  char *v4; // r11
  FCGI_BUFFER *v5; // r10
  unsigned int v6; // ebx
  __int16 v7; // dx
  int v8; // r9d
  __int64 v9; // r8
  __int16 v11; // cx
  int v12; // r8d
  __int64 v13; // rdx
  int v15; // [rsp+38h] [rbp+10h] BYREF

  Flink = a2->Flink;
  v15 = 0;
  if ( Flink->Blink != a2 || (v3 = Flink->Flink, Flink->Flink->Blink != Flink) )
    __fastfail(3u);
  a2->Flink = v3;
  v4 = (char *)this - 8;
  v5 = (FCGI_BUFFER *)&Flink[-2];
  v3->Blink = a2;
  if ( *((_DWORD *)this + 25) )
  {
    v6 = -2147023901;
    if ( v5 )
      FCGI_BUFFER::Free(v5);
  }
  else
  {
    v6 = 0;
    switch ( *((_DWORD *)v5 + 7) )
    {
      case 1:
        v11 = *((_WORD *)v4 + 20);
        *((_DWORD *)v4 + 11) = 3;
        v12 = *((_DWORD *)v5 + 6);
        v13 = *(_QWORD *)v5;
        *(_QWORD *)(v13 - 8) = 0;
        *(_BYTE *)(v13 - 6) = HIBYTE(v11);
        *(_BYTE *)(v13 - 4) = BYTE1(v12);
        *(_WORD *)(v13 - 8) = 1025;
        *(_BYTE *)(v13 - 5) = v11;
        *(_BYTE *)(v13 - 3) = v12;
        *((_DWORD *)v4 + 15) = 1;
        goto LABEL_10;
      case 2:
        return (unsigned int)PROTOCOL::BeginSendParamsNoEntity((PROTOCOL *)v4, v5, &v15);
      case 3:
        v7 = *((_WORD *)v4 + 20);
        *((_DWORD *)v4 + 11) = 5;
        v8 = *((_DWORD *)v5 + 6);
        v9 = *(_QWORD *)v5;
        *(_QWORD *)(v9 - 8) = 0;
        *(_BYTE *)(v9 - 6) = HIBYTE(v7);
        *(_BYTE *)(v9 - 4) = BYTE1(v8);
        *(_WORD *)(v9 - 8) = 1281;
        *(_BYTE *)(v9 - 5) = v7;
        *(_BYTE *)(v9 - 3) = v8;
        *((_DWORD *)v4 + 15) = 0;
LABEL_10:
        *((_QWORD *)v4 + 18) = v5;
        return (unsigned int)PROTOCOL::BeginSendCommon((PROTOCOL *)v4, &v15);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x1800039a0  push    rbx
0x1800039a2  sub     rsp, 20h
0x1800039a6  mov     r10, [rdx]
0x1800039a9  mov     [rsp+28h+arg_8], 0
0x1800039b1  cmp     [r10+8], rdx
0x1800039b5  jnz     loc_180003AC5
0x1800039bb  mov     rax, [r10]
0x1800039be  cmp     [rax+8], r10
0x1800039c2  jnz     loc_180003AC5
0x1800039c8  mov     [rdx], rax
0x1800039cb  lea     r11, [rcx-8]
0x1800039cf  add     r10, 0FFFFFFFFFFFFFFE0h
0x1800039d3  mov     [rax+8], rdx
0x1800039d7  cmp     dword ptr [r11+6Ch], 0
0x1800039dc  jnz     loc_180003AAB
0x1800039e2  mov     ecx, [r10+1Ch]
0x1800039e6  xor     ebx, ebx
0x1800039e8  sub     ecx, 1
0x1800039eb  jz      short loc_180003A51
0x1800039ed  sub     ecx, 1
0x1800039f0  jz      short loc_180003A3F
0x1800039f2  cmp     ecx, 1
0x1800039f5  jnz     loc_180003ABD
0x1800039fb  movzx   edx, word ptr [r11+28h]
0x180003a00  xor     eax, eax
0x180003a02  mov     dword ptr [r11+2Ch], 5
0x180003a0a  mov     r9d, [r10+18h]
0x180003a0e  mov     r8, [r10]
0x180003a11  mov     [r8-8], rax
0x180003a15  movzx   eax, dx
0x180003a18  sar     ax, 8
0x180003a1c  mov     [r8-6], al
0x180003a20  mov     eax, r9d
0x180003a23  shr     eax, 8
0x180003a26  mov     [r8-4], al
0x180003a2a  mov     word ptr [r8-8], 501h
0x180003a31  mov     [r8-5], dl
0x180003a35  mov     [r8-3], r9b
0x180003a39  mov     [r11+3Ch], ebx
0x180003a3d  jmp     short loc_180003A93
0x180003a3f  lea     r8, [rsp+28h+arg_8]; int *
0x180003a44  mov     rdx, r10; struct FCGI_BUFFER *
0x180003a47  mov     rcx, r11; this
0x180003a4a  call    ?BeginSendParamsNoEntity@PROTOCOL@@AEAAJPEAVFCGI_BUFFER@@PEAH@Z; PROTOCOL::BeginSendParamsNoEntity(FCGI_BUFFER *,int *)
0x180003a4f  jmp     short loc_180003AA7
0x180003a51  movzx   ecx, word ptr [r11+28h]
0x180003a56  xor     eax, eax
0x180003a58  mov     dword ptr [r11+2Ch], 3
0x180003a60  mov     r8d, [r10+18h]
0x180003a64  mov     rdx, [r10]
0x180003a67  mov     [rdx-8], rax
0x180003a6b  movzx   eax, cx
0x180003a6e  sar     ax, 8
0x180003a72  mov     [rdx-6], al
0x180003a75  mov     eax, r8d
0x180003a78  shr     eax, 8
0x180003a7b  mov     [rdx-4], al
0x180003a7e  mov     word ptr [rdx-8], 401h
0x180003a84  mov     [rdx-5], cl
0x180003a87  mov     [rdx-3], r8b
0x180003a8b  mov     dword ptr [r11+3Ch], 1
0x180003a93  lea     rdx, [rsp+28h+arg_8]; int *
0x180003a98  mov     [r11+90h], r10
0x180003a9f  mov     rcx, r11; this
0x180003aa2  call    ?BeginSendCommon@PROTOCOL@@AEAAJPEAH@Z; PROTOCOL::BeginSendCommon(int *)
0x180003aa7  mov     ebx, eax
0x180003aa9  jmp     short loc_180003ABD
0x180003aab  mov     ebx, 800703E3h
0x180003ab0  test    r10, r10
0x180003ab3  jz      short loc_180003ABD
0x180003ab5  mov     rcx, r10; this
0x180003ab8  call    ?Free@FCGI_BUFFER@@QEAAJXZ; FCGI_BUFFER::Free(void)
0x180003abd  mov     eax, ebx
0x180003abf  add     rsp, 20h
0x180003ac3  pop     rbx
0x180003ac4  retn
0x180003ac5  mov     ecx, 3
0x180003aca  int     29h; Win8: RtlFailFast(ecx)
```
