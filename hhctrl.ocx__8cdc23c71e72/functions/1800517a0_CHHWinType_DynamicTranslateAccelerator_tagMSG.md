# CHHWinType::DynamicTranslateAccelerator(tagMSG *)

- ea: `0x1800517a0`
- end: `0x180051921`
- name: `?DynamicTranslateAccelerator@CHHWinType@@QEAA_NPEAUtagMSG@@@Z`
- size: `385`
- prototype: `bool __fastcall(CHHWinType *__hidden this, LPMSG lpMsg)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18003540c`

## callees

- `0x180001710`
- `0x180001768`
- `0x180005a4c`
- `0x1800517a0`
- `0x1800523d8`
- `0x180053138`

## import_xrefs

- `USER32!CharUpperA` at `0x180051879`
- `USER32!CharUpperA` at `0x1800518b6`
- `USER32!CharUpperA` at `0x180051879`
- `USER32!CharUpperA` at `0x1800518b6`
- `USER32!LoadAcceleratorsA` at `0x1800517f5`
- `USER32!LoadAcceleratorsA` at `0x1800517f5`
- `USER32!CreateAcceleratorTableA` at `0x1800518e4`
- `USER32!CreateAcceleratorTableA` at `0x1800518e4`
- `USER32!TranslateAcceleratorA` at `0x180051907`
- `USER32!TranslateAcceleratorA` at `0x180051907`
- `USER32!IsWindow` at `0x1800517b9`
- `USER32!IsWindow` at `0x1800517b9`
- `USER32!CopyAcceleratorTableA` at `0x18005180d`
- `USER32!CopyAcceleratorTableA` at `0x18005184a`
- `USER32!CopyAcceleratorTableA` at `0x18005180d`
- `USER32!CopyAcceleratorTableA` at `0x18005184a`

## pseudocode

```c
bool __fastcall CHHWinType::DynamicTranslateAccelerator(CHHWinType *this, LPMSG lpMsg)
{
  bool v4; // bl
  HACCEL AcceleratorsA; // rbx
  HINSTANCE ResourceInstance; // rax
  __int64 v7; // rbp
  struct tagACCEL *v8; // rax
  struct tagACCEL *v9; // r14
  CResourceCache *v10; // rcx
  __int64 v11; // rbx
  unsigned __int8 v12; // al
  unsigned __int8 v13; // al
  int i; // esi
  int v15; // edx
  CResourceCache *v16; // rcx
  unsigned __int8 v17; // al

  v4 = 0;
  if ( !IsWindow(*((HWND *)this + 8)) )
    goto LABEL_14;
  if ( *((_QWORD *)this + 85) )
  {
LABEL_13:
    v4 = TranslateAcceleratorA(*((HWND *)this + 8), *((HACCEL *)this + 85), lpMsg) != 0;
LABEL_14:
    LOBYTE(v8) = v4;
    return (char)v8;
  }
  AcceleratorsA = hAccelSrc;
  if ( !hAccelSrc )
  {
    ResourceInstance = CHtmlHelpModule::GetResourceInstance((CHtmlHelpModule *)&_Module);
    AcceleratorsA = LoadAcceleratorsA(ResourceInstance, (LPCSTR)0x1781);
    hAccelSrc = AcceleratorsA;
  }
  v7 = CopyAcceleratorTableA(AcceleratorsA, 0, 0);
  v8 = (struct tagACCEL *)operator new[](saturated_mul(v7 + 21, 6u));
  v9 = v8;
  if ( v8 )
  {
    CopyAcceleratorTableA(AcceleratorsA, v8, v7);
    if ( (*((_DWORD *)this + 42) & 0x1000) != 0 )
    {
      v11 = v7;
      v9[v7].fVirt = 19;
      v12 = CResourceCache::TabCtrlKeys(v10, 20);
      v13 = (unsigned __int8)CharUpperA((LPSTR)v12);
      v9[v7].cmd = 208;
      LODWORD(v7) = v7 + 1;
      v9[v11].key = v13;
    }
    for ( i = 0; i < 20; ++i )
    {
      if ( (unsigned int)CHHWinType::IsValidNavPane(this, i) )
      {
        v9[(int)v7].fVirt = 19;
        v17 = CResourceCache::TabCtrlKeys(v16, v15);
        v9[(int)v7].key = (unsigned __int8)CharUpperA((LPSTR)v17);
        v9[(int)v7].cmd = i - 28672;
        LODWORD(v7) = v7 + 1;
      }
    }
    *((_QWORD *)this + 85) = CreateAcceleratorTableA(v9, v7);
    operator delete[](v9);
    goto LABEL_13;
  }
  return (char)v8;
}

```

## disassembly

```asm
0x1800517a0  push    rbx
0x1800517a2  push    rbp
0x1800517a3  push    rsi
0x1800517a4  push    rdi
0x1800517a5  push    r14
0x1800517a7  push    r15
0x1800517a9  sub     rsp, 28h
0x1800517ad  mov     rdi, rcx
0x1800517b0  mov     r15, rdx
0x1800517b3  mov     rcx, [rcx+40h]; hWnd
0x1800517b7  xor     bl, bl
0x1800517b9  call    cs:__imp_IsWindow
0x1800517bf  test    eax, eax
0x1800517c1  jz      loc_180051912
0x1800517c7  cmp     qword ptr [rdi+2A8h], 0
0x1800517cf  jnz     loc_1800518F9
0x1800517d5  mov     rbx, cs:hAccelSrc
0x1800517dc  test    rbx, rbx
0x1800517df  jnz     short loc_180051805
0x1800517e1  lea     rcx, ?_Module@@3VCHtmlHelpModule@@A; this
0x1800517e8  call    ?GetResourceInstance@CHtmlHelpModule@@QEAAPEAUHINSTANCE__@@XZ; CHtmlHelpModule::GetResourceInstance(void)
0x1800517ed  mov     rcx, rax; hInstance
0x1800517f0  mov     edx, 1781h; lpTableName
0x1800517f5  call    cs:__imp_LoadAcceleratorsA
0x1800517fb  mov     rbx, rax
0x1800517fe  mov     cs:hAccelSrc, rax
0x180051805  xor     r8d, r8d; cAccelEntries
0x180051808  xor     edx, edx; lpAccelDst
0x18005180a  mov     rcx, rbx; hAccelSrc
0x18005180d  call    cs:__imp_CopyAcceleratorTableA
0x180051813  movsxd  rbp, eax
0x180051816  mov     eax, 6
0x18005181b  lea     rcx, [rbp+15h]
0x18005181f  mul     rcx
0x180051822  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180051829  cmovb   rax, rcx
0x18005182d  mov     rcx, rax; unsigned __int64
0x180051830  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180051835  mov     r14, rax
0x180051838  test    rax, rax
0x18005183b  jz      loc_180051914
0x180051841  mov     r8d, ebp; cAccelEntries
0x180051844  mov     rdx, r14; lpAccelDst
0x180051847  mov     rcx, rbx; hAccelSrc
0x18005184a  call    cs:__imp_CopyAcceleratorTableA
0x180051850  test    dword ptr [rdi+0A8h], 1000h
0x18005185a  jz      short loc_180051892
0x18005185c  lea     rbx, ds:0[rbp*2]
0x180051864  mov     edx, 14h; int
0x180051869  add     rbx, rbp
0x18005186c  mov     byte ptr [r14+rbx*2], 13h
0x180051871  call    ?TabCtrlKeys@CResourceCache@@QEAADH@Z; CResourceCache::TabCtrlKeys(int)
0x180051876  movzx   ecx, al; lpsz
0x180051879  call    cs:__imp_CharUpperA
0x18005187f  mov     word ptr [r14+rbx*2+4], 0D0h
0x180051887  inc     ebp
0x180051889  movzx   ecx, al
0x18005188c  mov     [r14+rbx*2+2], cx
0x180051892  xor     esi, esi
0x180051894  mov     edx, esi; int
0x180051896  mov     rcx, rdi; this
0x180051899  call    ?IsValidNavPane@CHHWinType@@QEAAHH@Z; CHHWinType::IsValidNavPane(int)
0x18005189e  test    eax, eax
0x1800518a0  jz      short loc_1800518D8
0x1800518a2  movsxd  rax, ebp
0x1800518a5  lea     rbx, [rax+rax*2]
0x1800518a9  mov     byte ptr [r14+rbx*2], 13h
0x1800518ae  call    ?TabCtrlKeys@CResourceCache@@QEAADH@Z; CResourceCache::TabCtrlKeys(int)
0x1800518b3  movzx   ecx, al; lpsz
0x1800518b6  call    cs:__imp_CharUpperA
0x1800518bc  movzx   ecx, al
0x1800518bf  movzx   eax, si
0x1800518c2  mov     [r14+rbx*2+2], cx
0x1800518c8  mov     ecx, 7000h
0x1800518cd  sub     ax, cx
0x1800518d0  mov     [r14+rbx*2+4], ax
0x1800518d6  inc     ebp
0x1800518d8  inc     esi
0x1800518da  cmp     esi, 14h
0x1800518dd  jl      short loc_180051894
0x1800518df  mov     edx, ebp; cAccel
0x1800518e1  mov     rcx, r14; paccel
0x1800518e4  call    cs:__imp_CreateAcceleratorTableA
0x1800518ea  mov     rcx, r14; void *
0x1800518ed  mov     [rdi+2A8h], rax
0x1800518f4  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x1800518f9  mov     rdx, [rdi+2A8h]; hAccTable
0x180051900  mov     r8, r15; lpMsg
0x180051903  mov     rcx, [rdi+40h]; hWnd
0x180051907  call    cs:__imp_TranslateAcceleratorA
0x18005190d  test    eax, eax
0x18005190f  setnz   bl
0x180051912  mov     al, bl
0x180051914  add     rsp, 28h
0x180051918  pop     r15
0x18005191a  pop     r14
0x18005191c  pop     rdi
0x18005191d  pop     rsi
0x18005191e  pop     rbp
0x18005191f  pop     rbx
0x180051920  retn
```
