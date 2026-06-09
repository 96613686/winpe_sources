# ISAPI_REQUEST::WriteClient(unsigned __int64,uchar *,ulong,ulong)

- ea: `0x180010610`
- end: `0x180010769`
- name: `?WriteClient@ISAPI_REQUEST@@UEAAJ_KPEAEKK@Z`
- size: `345`
- prototype: `__int64 __fastcall(ISAPI_REQUEST *this, __int64, unsigned __int8 *, int, char)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180010610`
- `0x180013010`

## pseudocode

```c
__int64 __fastcall ISAPI_REQUEST::WriteClient(ISAPI_REQUEST *this, __int64 a2, unsigned __int8 *a3, int a4, char a5)
{
  int v5; // esi
  __int64 v9; // rax
  __int64 v10; // rdi
  __int64 result; // rax
  __int128 v12; // [rsp+40h] [rbp-48h] BYREF
  __int128 v13; // [rsp+50h] [rbp-38h]
  int v14; // [rsp+A8h] [rbp+20h] BYREF

  v5 = a5 & 2;
  v14 = 0;
  v12 = 0;
  v13 = 0;
  if ( a2 )
    *((_QWORD *)this + 2) = a2;
  if ( v5 )
    *((_DWORD *)this + 10) = 1;
  v9 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 32LL))(*((_QWORD *)this + 3));
  v10 = v9;
  if ( !*((_DWORD *)this + 12) )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 96LL))(v9);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 128LL))(v10);
  }
  LODWORD(v12) = 0;
  *((_QWORD *)&v12 + 1) = a3;
  LODWORD(v13) = a4;
  *((_DWORD *)this + 12) = 1;
  result = (*(__int64 (__fastcall **)(__int64, __int128 *, __int64, bool, int, int *, _QWORD))(*(_QWORD *)v10 + 168LL))(
             v10,
             &v12,
             1,
             v5 != 0,
             1,
             &v14,
             0);
  if ( (int)result >= 0 )
  {
    if ( *(_WORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v10 + 8LL))(v10) + 536) < 0x7D0u )
      return 0;
    result = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, int *, _QWORD))(*(_QWORD *)v10 + 144LL))(
               v10,
               0,
               1,
               &v14,
               0);
    if ( (int)result >= 0 )
      return 0;
  }
  if ( v5 )
    *((_DWORD *)this + 10) = 0;
  return result;
}

```

## disassembly

```asm
0x180010610  mov     rax, rsp
0x180010613  mov     [rax+8], rbx
0x180010617  mov     [rax+10h], rbp
0x18001061b  push    rsi
0x18001061c  push    rdi
0x18001061d  push    r13
0x18001061f  push    r14
0x180010621  push    r15
0x180010623  sub     rsp, 60h
0x180010627  mov     esi, [rsp+88h+arg_20]
0x18001062e  xorps   xmm0, xmm0
0x180010631  and     esi, 2
0x180010634  mov     dword ptr [rax+20h], 0
0x18001063b  mov     ebp, 0
0x180010640  mov     r14d, r9d
0x180010643  setnz   bpl
0x180010647  mov     r15, r8
0x18001064a  mov     rbx, rcx
0x18001064d  movups  xmmword ptr [rax-48h], xmm0
0x180010651  movups  xmmword ptr [rax-38h], xmm0
0x180010655  test    rdx, rdx
0x180010658  jz      short loc_18001065E
0x18001065a  mov     [rcx+10h], rdx
0x18001065e  mov     r13d, 1
0x180010664  test    esi, esi
0x180010666  jz      short loc_18001066C
0x180010668  mov     [rcx+28h], r13d
0x18001066c  mov     rcx, [rcx+18h]
0x180010670  mov     rax, [rcx]
0x180010673  mov     rax, [rax+20h]
0x180010677  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001067c  cmp     dword ptr [rbx+30h], 0
0x180010680  mov     rdi, rax
0x180010683  jnz     short loc_1800106A6
0x180010685  mov     rcx, [rax]
0x180010688  mov     rax, [rcx+60h]
0x18001068c  mov     rcx, rdi
0x18001068f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010694  mov     rcx, [rdi]
0x180010697  mov     rax, [rcx+80h]
0x18001069e  mov     rcx, rdi
0x1800106a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800106a6  mov     [rsp+88h+var_48], 0
0x1800106ae  lea     rcx, [rsp+88h+arg_18]
0x1800106b6  mov     [rsp+88h+var_40], r15
0x1800106bb  lea     rdx, [rsp+88h+var_48]
0x1800106c0  mov     dword ptr [rsp+88h+var_38], r14d
0x1800106c5  mov     r9d, ebp
0x1800106c8  mov     [rbx+30h], r13d
0x1800106cc  mov     r8d, r13d
0x1800106cf  mov     rax, [rdi]
0x1800106d2  mov     [rsp+88h+var_58], 0
0x1800106db  mov     [rsp+88h+var_60], rcx
0x1800106e0  mov     rcx, rdi
0x1800106e3  mov     dword ptr [rsp+88h+var_68], r13d
0x1800106e8  mov     rax, [rax+0A8h]
0x1800106ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800106f4  test    eax, eax
0x1800106f6  js      short loc_180010745
0x1800106f8  mov     rax, [rdi]
0x1800106fb  mov     rcx, rdi
0x1800106fe  mov     rax, [rax+8]
0x180010702  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010707  mov     ecx, 7D0h
0x18001070c  cmp     [rax+218h], cx
0x180010713  jb      short loc_180010741
0x180010715  mov     rax, [rdi]
0x180010718  lea     r9, [rsp+88h+arg_18]
0x180010720  mov     r8d, r13d
0x180010723  mov     [rsp+88h+var_68], 0
0x18001072c  xor     edx, edx
0x18001072e  mov     rcx, rdi
0x180010731  mov     rax, [rax+90h]
0x180010738  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001073d  test    eax, eax
0x18001073f  js      short loc_180010745
0x180010741  xor     eax, eax
0x180010743  jmp     short loc_180010750
0x180010745  test    esi, esi
0x180010747  jz      short loc_180010750
0x180010749  mov     dword ptr [rbx+28h], 0
0x180010750  lea     r11, [rsp+88h+var_28]
0x180010755  mov     rbx, [r11+30h]
0x180010759  mov     rbp, [r11+38h]
0x18001075d  mov     rsp, r11
0x180010760  pop     r15
0x180010762  pop     r14
0x180010764  pop     r13
0x180010766  pop     rdi
0x180010767  pop     rsi
0x180010768  retn
```
