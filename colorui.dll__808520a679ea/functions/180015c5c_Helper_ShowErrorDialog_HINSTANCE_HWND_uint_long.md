# Helper::ShowErrorDialog(HINSTANCE__ *,HWND__ *,uint,long)

- ea: `0x180015c5c`
- end: `0x180015cbf`
- name: `?ShowErrorDialog@Helper@@YAJPEAUHINSTANCE__@@PEAUHWND__@@IJ@Z`
- size: `99`
- prototype: `__int64 __fastcall(HINSTANCE this, HINSTANCE, HWND, unsigned int)`
- caller_count: `8`
- callee_count: `4`
- tags: ``

## callers

- `0x18000cd90`
- `0x18000d338`
- `0x18000d7dc`
- `0x18000f074`
- `0x18000f654`
- `0x180014870`
- `0x180016a70`
- `0x180016fa8`

## callees

- `0x180015c5c`
- `0x180015cc8`
- `0x18001772c`
- `0x1800179f0`

## pseudocode

```c
__int64 __fastcall Helper::ShowErrorDialog(HINSTANCE this, HINSTANCE a2, HWND a3, unsigned int a4)
{
  int StringFromRC; // ebx
  int v9; // [rsp+20h] [rbp-38h] BYREF
  HWND v10; // [rsp+28h] [rbp-30h]

  v9 = 1735554163;
  v10 = (HWND)&NCoreLibrary::TString::gszNullState;
  StringFromRC = NCoreLibrary::TString::LoadStringFromRC((NCoreLibrary::TString *)&v9, this, (UINT)a3);
  if ( StringFromRC >= 0 )
    StringFromRC = Helper::ShowErrorDialog(this, a2, v10, (const unsigned __int16 *)a4, v9);
  NCoreLibrary::TString::~TString((NCoreLibrary::TString *)&v9);
  return (unsigned int)StringFromRC;
}

```

## disassembly

```asm
0x180015c5c  push    rbx
0x180015c5e  push    rbp
0x180015c5f  push    rsi
0x180015c60  push    rdi
0x180015c61  sub     rsp, 38h
0x180015c65  mov     rbp, rdx
0x180015c68  mov     [rsp+58h+var_38], 67727473h; int
0x180015c70  mov     rdx, rcx; HINSTANCE
0x180015c73  lea     rax, ?gszNullState@TString@NCoreLibrary@@0PAGA; ushort near * NCoreLibrary::TString::gszNullState
0x180015c7a  mov     rdi, rcx
0x180015c7d  mov     [rsp+58h+var_30], rax
0x180015c82  lea     rcx, [rsp+58h+var_38]; this
0x180015c87  mov     esi, r9d
0x180015c8a  call    ?LoadStringFromRC@TString@NCoreLibrary@@QEAAJPEAUHINSTANCE__@@I@Z; NCoreLibrary::TString::LoadStringFromRC(HINSTANCE__ *,uint)
0x180015c8f  mov     ebx, eax
0x180015c91  test    eax, eax
0x180015c93  js      short loc_180015CAA
0x180015c95  mov     r8, [rsp+58h+var_30]; HWND
0x180015c9a  mov     r9d, esi; unsigned __int16 *
0x180015c9d  mov     rdx, rbp; HINSTANCE
0x180015ca0  mov     rcx, rdi; this
0x180015ca3  call    ?ShowErrorDialog@Helper@@YAJPEAUHINSTANCE__@@PEAUHWND__@@PEBGJ@Z; Helper::ShowErrorDialog(HINSTANCE__ *,HWND__ *,ushort const *,long)
0x180015ca8  mov     ebx, eax
0x180015caa  lea     rcx, [rsp+58h+var_38]; this
0x180015caf  call    ??1TString@NCoreLibrary@@QEAA@XZ; NCoreLibrary::TString::~TString(void)
0x180015cb4  mov     eax, ebx
0x180015cb6  add     rsp, 38h
0x180015cba  pop     rdi
0x180015cbb  pop     rsi
0x180015cbc  pop     rbp
0x180015cbd  pop     rbx
0x180015cbe  retn
```
