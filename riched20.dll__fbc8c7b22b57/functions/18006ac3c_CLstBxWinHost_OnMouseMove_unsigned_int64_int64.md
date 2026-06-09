# CLstBxWinHost::OnMouseMove(unsigned __int64,__int64)

- ea: `0x18006ac3c`
- end: `0x18006adec`
- name: `?OnMouseMove@CLstBxWinHost@@QEAA_J_K_J@Z`
- size: `432`
- prototype: `__int64 __fastcall(CLstBxWinHost *__hidden this, unsigned __int64, __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18006b190`
- `0x18006bb30`

## callees

- `0x180063960`
- `0x180068360`
- `0x180069bac`
- `0x18006ac3c`
- `0x18006b234`
- `0x18006b2f4`
- `0x180095010`

## import_xrefs

- `USER32!PtInRect` at `0x18006ac84`
- `USER32!PtInRect` at `0x18006ac84`

## pseudocode

```c
__int64 __fastcall CLstBxWinHost::OnMouseMove(CLstBxWinHost *this, __int64 a2, __int64 a3)
{
  int v3; // ebp
  int v6; // r14d
  int ItemFromPoint; // esi
  int v8; // ecx
  int v9; // eax
  int *v10; // r8
  int v11; // ebp
  int v12; // edx
  struct tagPOINT v14; // [rsp+48h] [rbp+10h] BYREF

  v3 = (__int16)a3;
  v6 = SWORD1(a3);
  v14.x = (__int16)a3;
  v14.y = SWORD1(a3);
  if ( *((_QWORD *)this + 285) == a3 && PtInRect((const RECT *)((char *)this + 164), v14) )
    return 0;
  *((_QWORD *)this + 285) = a3;
  ItemFromPoint = CLstBxWinHost::GetItemFromPoint(this, &v14);
  if ( (*((_BYTE *)this + 128) & 0x40) == 0 )
  {
    if ( !(unsigned int)CLstBxWinHost::PointInRect(this, &v14) )
      return 0;
LABEL_27:
    if ( ItemFromPoint != *((_DWORD *)this + 50)
      || *((_DWORD *)this + 33) == 8
      && ItemFromPoint >= 0
      && !(unsigned int)CLstBxWinHost::IsSelected(this, ItemFromPoint) )
    {
      CLstBxWinHost::MouseMoveHelper(this, ItemFromPoint, 1);
    }
    return 0;
  }
  if ( v6 < 0 )
  {
    v9 = -v6;
  }
  else
  {
    v8 = *((_DWORD *)this + 44);
    if ( v6 <= v8 - 1 )
    {
      if ( *((_DWORD *)this + 33) == 8 && (v3 < 0 || v3 > *((_DWORD *)this + 43) - 1) )
        return 0;
      goto LABEL_27;
    }
    LOWORD(v9) = v6 - v8 + 1;
  }
  v10 = (int *)((char *)this + 192);
  v11 = 250 - 16 * (unsigned __int16)v9;
  if ( v6 > 0 )
  {
    v12 = *v10 - 1;
    if ( v12 >= ItemFromPoint + 1 )
      v12 = ItemFromPoint + 1;
  }
  else
  {
    v12 = 0;
    if ( ItemFromPoint - 1 >= 0 )
      v12 = ItemFromPoint - 1;
  }
  if ( v12 >= 0 && v12 < *v10 )
  {
    if ( v12 != *((_DWORD *)this + 50) )
      CLstBxWinHost::MouseMoveHelper(this, v12, *((_DWORD *)this + 33) != 8);
    CLstBxWinHost::OnVScroll(this, (unsigned __int64)(unsigned int)~v6 >> 31, (__int64)v10);
  }
  if ( v11 < 5 )
    v11 = 5;
  (*(void (__fastcall **)(CLstBxWinHost *, __int64, _QWORD))(*(_QWORD *)this + 112LL))(this, 28988, (unsigned int)v11);
  return 0;
}

```

## disassembly

```asm
0x18006ac3c  mov     r11, rsp
0x18006ac3f  mov     [r11+8], rbx
0x18006ac43  mov     [r11+18h], rbp
0x18006ac47  mov     [r11+10h], rdx
0x18006ac4b  push    rsi
0x18006ac4c  push    rdi
0x18006ac4d  push    r14
0x18006ac4f  sub     rsp, 20h
0x18006ac53  mov     eax, r8d
0x18006ac56  movsx   ebp, r8w
0x18006ac5a  shr     rax, 10h
0x18006ac5e  mov     rdi, r8
0x18006ac61  mov     rbx, rcx
0x18006ac64  movsx   r14d, ax
0x18006ac68  mov     [rsp+38h+arg_8.x], ebp
0x18006ac6c  mov     [r11+14h], r14d
0x18006ac70  cmp     [rcx+8E8h], r8
0x18006ac77  jnz     short loc_18006AC98
0x18006ac79  mov     rdx, [r11+10h]; pt
0x18006ac7d  add     rcx, 0A4h; lprc
0x18006ac84  call    cs:__imp_PtInRect
0x18006ac8b  nop     dword ptr [rax+rax+00h]
0x18006ac90  test    eax, eax
0x18006ac92  jnz     loc_18006ADD6
0x18006ac98  lea     rdx, [rsp+38h+arg_8]; struct tagPOINT *
0x18006ac9d  mov     [rbx+8E8h], rdi
0x18006aca4  mov     rcx, rbx; this
0x18006aca7  call    ?GetItemFromPoint@CLstBxWinHost@@QEAAHPEBUtagPOINT@@@Z; CLstBxWinHost::GetItemFromPoint(tagPOINT const *)
0x18006acac  test    byte ptr [rbx+80h], 40h
0x18006acb3  mov     esi, eax
0x18006acb5  jz      loc_18006AD92
0x18006acbb  mov     edi, r14d
0x18006acbe  test    r14d, r14d
0x18006acc1  js      short loc_18006AD03
0x18006acc3  mov     ecx, [rbx+0B0h]
0x18006acc9  lea     eax, [rcx-1]
0x18006accc  cmp     r14d, eax
0x18006accf  jg      short loc_18006ACFB
0x18006acd1  cmp     dword ptr [rbx+84h], 8
0x18006acd8  jnz     loc_18006ADA3
0x18006acde  test    ebp, ebp
0x18006ace0  js      loc_18006ADD6
0x18006ace6  mov     eax, [rbx+0ACh]
0x18006acec  dec     eax
0x18006acee  cmp     ebp, eax
0x18006acf0  jg      loc_18006ADD6
0x18006acf6  jmp     loc_18006ADA3
0x18006acfb  mov     eax, edi
0x18006acfd  sub     eax, ecx
0x18006acff  inc     eax
0x18006ad01  jmp     short loc_18006AD07
0x18006ad03  mov     eax, edi
0x18006ad05  neg     eax
0x18006ad07  movzx   eax, ax
0x18006ad0a  lea     r8, [rbx+0C0h]
0x18006ad11  shl     eax, 4
0x18006ad14  mov     ebp, 0FAh
0x18006ad19  sub     ebp, eax
0x18006ad1b  test    edi, edi
0x18006ad1d  jg      short loc_18006AD2B
0x18006ad1f  lea     eax, [rsi-1]
0x18006ad22  xor     edx, edx
0x18006ad24  test    eax, eax
0x18006ad26  cmovns  edx, eax
0x18006ad29  jmp     short loc_18006AD38
0x18006ad2b  mov     edx, [r8]
0x18006ad2e  lea     ecx, [rsi+1]
0x18006ad31  dec     edx
0x18006ad33  cmp     edx, ecx
0x18006ad35  cmovge  edx, ecx; int
0x18006ad38  test    edx, edx
0x18006ad3a  js      short loc_18006AD6F
0x18006ad3c  cmp     edx, [r8]
0x18006ad3f  jge     short loc_18006AD6F
0x18006ad41  cmp     edx, [rbx+0C8h]
0x18006ad47  jz      short loc_18006AD5F
0x18006ad49  xor     r8d, r8d
0x18006ad4c  mov     rcx, rbx; this
0x18006ad4f  cmp     dword ptr [rbx+84h], 8
0x18006ad56  setnz   r8b; int
0x18006ad5a  call    ?MouseMoveHelper@CLstBxWinHost@@IEAAXHH@Z; CLstBxWinHost::MouseMoveHelper(int,int)
0x18006ad5f  not     edi
0x18006ad61  mov     rcx, rbx; this
0x18006ad64  mov     edx, edi
0x18006ad66  shr     rdx, 1Fh; unsigned __int64
0x18006ad6a  call    ?OnVScroll@CLstBxWinHost@@QEAA_J_K_J@Z; CLstBxWinHost::OnVScroll(unsigned __int64,__int64)
0x18006ad6f  mov     rax, [rbx]
0x18006ad72  mov     ecx, 5
0x18006ad77  cmp     ebp, ecx
0x18006ad79  mov     edx, 713Ch
0x18006ad7e  cmovl   ebp, ecx
0x18006ad81  mov     rcx, rbx
0x18006ad84  mov     rax, [rax+70h]
0x18006ad88  mov     r8d, ebp
0x18006ad8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ad90  jmp     short loc_18006ADD6
0x18006ad92  lea     rdx, [rsp+38h+arg_8]; struct tagPOINT *
0x18006ad97  mov     rcx, rbx; this
0x18006ad9a  call    ?PointInRect@CLstBxWinHost@@QEAAHPEBUtagPOINT@@@Z; CLstBxWinHost::PointInRect(tagPOINT const *)
0x18006ad9f  test    eax, eax
0x18006ada1  jz      short loc_18006ADD6
0x18006ada3  cmp     esi, [rbx+0C8h]
0x18006ada9  jnz     short loc_18006ADC6
0x18006adab  cmp     dword ptr [rbx+84h], 8
0x18006adb2  jnz     short loc_18006ADD6
0x18006adb4  test    esi, esi
0x18006adb6  js      short loc_18006ADD6
0x18006adb8  mov     edx, esi; int
0x18006adba  mov     rcx, rbx; this
0x18006adbd  call    ?IsSelected@CLstBxWinHost@@QEAAHJ@Z; CLstBxWinHost::IsSelected(long)
0x18006adc2  test    eax, eax
0x18006adc4  jnz     short loc_18006ADD6
0x18006adc6  mov     r8d, 1; int
0x18006adcc  mov     edx, esi; int
0x18006adce  mov     rcx, rbx; this
0x18006add1  call    ?MouseMoveHelper@CLstBxWinHost@@IEAAXHH@Z; CLstBxWinHost::MouseMoveHelper(int,int)
0x18006add6  mov     rbx, [rsp+38h+arg_0]
0x18006addb  xor     eax, eax
0x18006addd  mov     rbp, [rsp+38h+arg_10]
0x18006ade2  add     rsp, 20h
0x18006ade6  pop     r14
0x18006ade8  pop     rdi
0x18006ade9  pop     rsi
0x18006adea  retn
```
