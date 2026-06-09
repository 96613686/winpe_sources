# GetEscapementVector(HDC__ *,int,tagPOINT &)

- ea: `0x180015700`
- end: `0x180015966`
- name: `?GetEscapementVector@@YAJPEAUHDC__@@HAEAUtagPOINT@@@Z`
- size: `614`
- prototype: `__int64 __fastcall(HDC hdc, int, struct tagPOINT *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18009ac00`

## callees

- `0x18000d6c0`
- `0x180014240`
- `0x180015700`
- `0x180015970`
- `0x180016900`
- `0x18001fe20`
- `0x180021fe0`
- `0x180029790`
- `0x18007ac50`

## import_xrefs

- `GDI32!DeleteDC` at `0x180015931`
- `GDI32!DeleteDC` at `0x180015931`
- `GDI32!ExtTextOutW` at `0x1800157d3`
- `GDI32!ExtTextOutW` at `0x180015918`
- `GDI32!ExtTextOutW` at `0x1800157d3`
- `GDI32!ExtTextOutW` at `0x180015918`
- `GDI32!MoveToEx` at `0x18001578e`
- `GDI32!MoveToEx` at `0x1800157f8`
- `GDI32!MoveToEx` at `0x1800158e3`
- `GDI32!MoveToEx` at `0x18001578e`
- `GDI32!MoveToEx` at `0x1800157f8`
- `GDI32!MoveToEx` at `0x1800158e3`
- `GDI32!SelectObject` at `0x18001589a`
- `GDI32!SelectObject` at `0x18001589a`
- `GDI32!SetBkMode` at `0x18001577d`
- `GDI32!SetBkMode` at `0x180015823`
- `GDI32!SetBkMode` at `0x1800158d2`
- `GDI32!SetBkMode` at `0x18001577d`
- `GDI32!SetBkMode` at `0x180015823`
- `GDI32!SetBkMode` at `0x1800158d2`
- `GDI32!SetTextAlign` at `0x18001576f`
- `GDI32!SetTextAlign` at `0x180015803`
- `GDI32!SetTextAlign` at `0x1800158c4`
- `GDI32!SetTextAlign` at `0x18001576f`
- `GDI32!SetTextAlign` at `0x180015803`
- `GDI32!SetTextAlign` at `0x1800158c4`

## pseudocode

```c
__int64 __fastcall GetEscapementVector(HDC hdc, __int64 a2, struct tagPOINT *a3)
{
  UINT TextAlign; // ebp
  int BkMode; // edi
  void *DCObject; // r15
  HDC CompatibleDC; // rax
  HDC v10; // r14
  UINT v11; // eax
  INT lpDx; // [rsp+40h] [rbp-58h] BYREF
  struct tagPOINT pt; // [rsp+48h] [rbp-50h] BYREF
  RECT rect; // [rsp+50h] [rbp-48h] BYREF

  lpDx = 1000;
  if ( !hdc )
    return 2147942487LL;
  pt = 0;
  TextAlign = GetTextAlign(hdc);
  GetCurrentPositionEx(hdc, &pt);
  BkMode = GetBkMode(hdc);
  SetTextAlign(hdc, TextAlign & 0xFFFFFFF8 | 1);
  SetBkMode(hdc, 1);
  MoveToEx(hdc, 0, 0, 0);
  rect = 0;
  ExtTextOutW(hdc, 0, 0, 0x1004u, &rect, L" ", 1u, &lpDx);
  GetCurrentPositionEx(hdc, a3);
  if ( !*(_QWORD *)a3 )
  {
    a3->x = lpDx;
    DCObject = (void *)GetDCObject(hdc, 655360);
    if ( DCObject )
    {
      CompatibleDC = CreateCompatibleDC(hdc);
      v10 = CompatibleDC;
      if ( CompatibleDC )
      {
        SelectObject(CompatibleDC, DCObject);
        if ( GetGraphicsMode(hdc) == 2 )
          SetGraphicsMode(v10, 2);
        v11 = GetTextAlign(v10);
        SetTextAlign(v10, v11 & 0xFFFFFFF8 | 1);
        SetBkMode(v10, 1);
        MoveToEx(v10, 0, 0, 0);
        ExtTextOutW(v10, 0, 0, 0x1000u, &rect, L" ", 1u, &lpDx);
        GetCurrentPositionEx(v10, a3);
        if ( !a3->x && !a3->y )
          a3->x = lpDx;
        DeleteDC(v10);
      }
    }
  }
  MoveToEx(hdc, pt.x, pt.y, 0);
  SetTextAlign(hdc, TextAlign);
  if ( BkMode != 1 )
    SetBkMode(hdc, BkMode);
  return 0;
}

```

## disassembly

```asm
0x180015700  mov     r11, rsp
0x180015703  push    rbx
0x180015704  push    rsi
0x180015705  sub     rsp, 88h
0x18001570c  mov     rax, cs:__security_cookie
0x180015713  xor     rax, rsp
0x180015716  mov     [rsp+98h+var_38], rax
0x18001571b  mov     [rsp+98h+var_58], 3E8h
0x180015723  mov     rsi, r8
0x180015726  mov     rbx, rcx
0x180015729  test    rcx, rcx
0x18001572c  jz      loc_18001584A
0x180015732  mov     [r11+10h], rbp
0x180015736  mov     [r11+20h], rdi
0x18001573a  mov     [r11-18h], r12
0x18001573e  mov     qword ptr [r11-50h], 0
0x180015746  call    GetTextAlign
0x18001574b  lea     rdx, [rsp+98h+pt]; lppt
0x180015750  mov     rcx, rbx; hdc
0x180015753  mov     ebp, eax
0x180015755  call    GetCurrentPositionEx
0x18001575a  mov     rcx, rbx; hdc
0x18001575d  call    GetBkMode
0x180015762  mov     edx, ebp
0x180015764  mov     rcx, rbx; hdc
0x180015767  and     edx, 0FFFFFFF9h
0x18001576a  mov     edi, eax
0x18001576c  or      edx, 1; align
0x18001576f  call    cs:__imp_SetTextAlign
0x180015775  mov     edx, 1; mode
0x18001577a  mov     rcx, rbx; hdc
0x18001577d  call    cs:__imp_SetBkMode
0x180015783  xor     r9d, r9d; lppt
0x180015786  xor     r8d, r8d; y
0x180015789  xor     edx, edx; x
0x18001578b  mov     rcx, rbx; hdc
0x18001578e  call    cs:__imp_MoveToEx
0x180015794  lea     rax, [rsp+98h+var_58]
0x180015799  xorps   xmm0, xmm0
0x18001579c  mov     [rsp+98h+lpDx], rax; lpDx
0x1800157a1  lea     r12, String; " "
0x1800157a8  mov     [rsp+98h+c], 1; c
0x1800157b0  lea     rax, [rsp+98h+rect]
0x1800157b5  mov     [rsp+98h+lpString], r12; lpString
0x1800157ba  mov     r9d, 1004h; options
0x1800157c0  xor     r8d, r8d; y
0x1800157c3  mov     [rsp+98h+lprect], rax; lprect
0x1800157c8  xor     edx, edx; x
0x1800157ca  mov     rcx, rbx; hdc
0x1800157cd  movdqu  xmmword ptr [rsp+98h+rect.left], xmm0
0x1800157d3  call    cs:__imp_ExtTextOutW
0x1800157d9  mov     rdx, rsi; lppt
0x1800157dc  mov     rcx, rbx; hdc
0x1800157df  call    GetCurrentPositionEx
0x1800157e4  cmp     dword ptr [rsi], 0
0x1800157e7  jz      short loc_180015851
0x1800157e9  mov     r8d, [rsp+98h+pt.y]; y
0x1800157ee  xor     r9d, r9d; lppt
0x1800157f1  mov     edx, [rsp+98h+pt.x]; x
0x1800157f5  mov     rcx, rbx; hdc
0x1800157f8  call    cs:__imp_MoveToEx
0x1800157fe  mov     edx, ebp; align
0x180015800  mov     rcx, rbx; hdc
0x180015803  call    cs:__imp_SetTextAlign
0x180015809  mov     r12, [rsp+98h+var_18]
0x180015811  mov     rbp, [rsp+98h+arg_8]
0x180015819  cmp     edi, 1
0x18001581c  jz      short loc_180015829
0x18001581e  mov     edx, edi; mode
0x180015820  mov     rcx, rbx; hdc
0x180015823  call    cs:__imp_SetBkMode
0x180015829  mov     rdi, [rsp+98h+arg_18]
0x180015831  xor     eax, eax
0x180015833  mov     rcx, [rsp+98h+var_38]
0x180015838  xor     rcx, rsp; StackCookie
0x18001583b  call    __security_check_cookie
0x180015840  add     rsp, 88h
0x180015847  pop     rsi
0x180015848  pop     rbx
0x180015849  retn
0x18001584a  mov     eax, 80070057h
0x18001584f  jmp     short loc_180015833
0x180015851  cmp     dword ptr [rsi+4], 0
0x180015855  jnz     short loc_1800157E9
0x180015857  mov     eax, [rsp+98h+var_58]
0x18001585b  mov     edx, 0A0000h
0x180015860  mov     rcx, rbx
0x180015863  mov     [rsi], eax
0x180015865  mov     [rsp+98h+var_28], r15
0x18001586a  call    GetDCObject
0x18001586f  mov     r15, rax
0x180015872  test    rax, rax
0x180015875  jz      loc_18001593C
0x18001587b  mov     rcx, rbx; hdc
0x18001587e  mov     [rsp+98h+var_20], r14
0x180015883  call    CreateCompatibleDC
0x180015888  mov     r14, rax
0x18001588b  test    rax, rax
0x18001588e  jz      loc_180015937
0x180015894  mov     rdx, r15; h
0x180015897  mov     rcx, rax; hdc
0x18001589a  call    cs:__imp_SelectObject
0x1800158a0  mov     rcx, rbx; hdc
0x1800158a3  call    GetGraphicsMode
0x1800158a8  cmp     eax, 2
0x1800158ab  jz      loc_180015946
0x1800158b1  mov     rcx, r14; hdc
0x1800158b4  call    GetTextAlign
0x1800158b9  and     eax, 0FFFFFFF9h
0x1800158bc  mov     rcx, r14; hdc
0x1800158bf  or      eax, 1
0x1800158c2  mov     edx, eax; align
0x1800158c4  call    cs:__imp_SetTextAlign
0x1800158ca  mov     edx, 1; mode
0x1800158cf  mov     rcx, r14; hdc
0x1800158d2  call    cs:__imp_SetBkMode
0x1800158d8  xor     r9d, r9d; lppt
0x1800158db  xor     r8d, r8d; y
0x1800158de  xor     edx, edx; x
0x1800158e0  mov     rcx, r14; hdc
0x1800158e3  call    cs:__imp_MoveToEx
0x1800158e9  lea     rax, [rsp+98h+var_58]
0x1800158ee  mov     r9d, 1000h; options
0x1800158f4  mov     [rsp+98h+lpDx], rax; lpDx
0x1800158f9  xor     r8d, r8d; y
0x1800158fc  mov     [rsp+98h+c], 1; c
0x180015904  lea     rax, [rsp+98h+rect]
0x180015909  mov     [rsp+98h+lpString], r12; lpString
0x18001590e  xor     edx, edx; x
0x180015910  mov     rcx, r14; hdc
0x180015913  mov     [rsp+98h+lprect], rax; lprect
0x180015918  call    cs:__imp_ExtTextOutW
0x18001591e  mov     rdx, rsi; lppt
0x180015921  mov     rcx, r14; hdc
0x180015924  call    GetCurrentPositionEx
0x180015929  cmp     dword ptr [rsi], 0
0x18001592c  jz      short loc_180015958
0x18001592e  mov     rcx, r14; hdc
0x180015931  call    cs:__imp_DeleteDC
0x180015937  mov     r14, [rsp+98h+var_20]
0x18001593c  mov     r15, [rsp+98h+var_28]
0x180015941  jmp     loc_1800157E9
0x180015946  mov     edx, 2; iMode
0x18001594b  mov     rcx, r14; hdc
0x18001594e  call    SetGraphicsMode
0x180015953  jmp     loc_1800158B1
0x180015958  cmp     dword ptr [rsi+4], 0
0x18001595c  jnz     short loc_18001592E
0x18001595e  mov     eax, [rsp+98h+var_58]
0x180015962  mov     [rsi], eax
0x180015964  jmp     short loc_18001592E
```
