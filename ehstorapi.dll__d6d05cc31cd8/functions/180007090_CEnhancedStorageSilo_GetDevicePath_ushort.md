# CEnhancedStorageSilo::GetDevicePath(ushort * *)

- ea: `0x180007090`
- end: `0x1800071af`
- name: `?GetDevicePath@CEnhancedStorageSilo@@UEAAJPEAPEAG@Z`
- size: `287`
- prototype: `__int64 __fastcall(CEnhancedStorageSilo *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task`

## callees

- `0x180003ce0`
- `0x180003df0`
- `0x180003ed0`
- `0x1800060e8`
- `0x1800061c8`
- `0x1800065ac`
- `0x180007090`
- `0x18000c4f0`

## string_xrefs

- `0x1800070f8`: `CEnhancedStorageSilo::GetDevicePath`
- `0x180007123`: `ppwszSiloDevicePath != NULL`

## pseudocode

```c
__int64 __fastcall CEnhancedStorageSilo::GetDevicePath(const unsigned __int16 **this, unsigned __int16 **a2)
{
  unsigned int v4; // ebx
  unsigned __int16 *v5; // rax
  int v7[4]; // [rsp+20h] [rbp-138h] BYREF
  _BYTE v8[272]; // [rsp+30h] [rbp-128h] BYREF

  v7[0] = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, &WPP_cf54b1e076d23b7381661ccc00326d94_Traceguids, a2);
  CESTTrackFn::CESTTrackFn((CESTTrackFn *)v8, "CEnhancedStorageSilo::GetDevicePath", v7);
  if ( a2 )
  {
    v5 = ATL::AtlAllocTaskWideString(this[8]);
    *a2 = v5;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, &WPP_cf54b1e076d23b7381661ccc00326d94_Traceguids, v5);
    v4 = v7[0];
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        56,
        &WPP_cf54b1e076d23b7381661ccc00326d94_Traceguids,
        "ppwszSiloDevicePath != NULL");
    v4 = -2147024809;
  }
  CESTTrackFn::~CESTTrackFn((CESTTrackFn *)v8);
  return v4;
}

```

## disassembly

```asm
0x180007090  mov     [rsp+arg_10], rbx
0x180007095  mov     [rsp+arg_18], rsi
0x18000709a  push    rdi
0x18000709b  sub     rsp, 150h
0x1800070a2  mov     rax, cs:__security_cookie
0x1800070a9  xor     rax, rsp
0x1800070ac  mov     [rsp+158h+var_18], rax
0x1800070b4  mov     rbx, rdx
0x1800070b7  mov     rdi, rcx
0x1800070ba  mov     [rsp+158h+var_138], 0
0x1800070c2  lea     rsi, WPP_GLOBAL_Control
0x1800070c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800070d0  cmp     rcx, rsi
0x1800070d3  jz      short loc_1800070F3
0x1800070d5  test    byte ptr [rcx+1Ch], 10h
0x1800070d9  jz      short loc_1800070F3
0x1800070db  mov     edx, 37h ; '7'
0x1800070e0  mov     r9, rbx
0x1800070e3  lea     r8, WPP_cf54b1e076d23b7381661ccc00326d94_Traceguids
0x1800070ea  mov     rcx, [rcx+10h]
0x1800070ee  call    WPP_SF_q
0x1800070f3  lea     r8, [rsp+158h+var_138]; int *
0x1800070f8  lea     rdx, aCenhancedstora_16; "CEnhancedStorageSilo::GetDevicePath"
0x1800070ff  lea     rcx, [rsp+158h+var_128]; this
0x180007104  call    ??0CESTTrackFn@@QEAA@PEBDPEAJ@Z; CESTTrackFn::CESTTrackFn(char const *,long *)
0x180007109  test    rbx, rbx
0x18000710c  jnz     short loc_180007141
0x18000710e  mov     rcx, cs:WPP_GLOBAL_Control
0x180007115  cmp     rcx, rsi
0x180007118  jz      short loc_18000713A
0x18000711a  test    byte ptr [rcx+1Ch], 2
0x18000711e  jz      short loc_18000713A
0x180007120  lea     edx, [rbx+38h]
0x180007123  lea     r9, aPpwszsilodevic; "ppwszSiloDevicePath != NULL"
0x18000712a  lea     r8, WPP_cf54b1e076d23b7381661ccc00326d94_Traceguids
0x180007131  mov     rcx, [rcx+10h]
0x180007135  call    WPP_SF_s
0x18000713a  mov     ebx, 80070057h
0x18000713f  jmp     short loc_18000717E
0x180007141  mov     rcx, [rdi+40h]; Source
0x180007145  call    ?AtlAllocTaskWideString@ATL@@YAPEAGPEBG@Z; ATL::AtlAllocTaskWideString(ushort const *)
0x18000714a  mov     [rbx], rax
0x18000714d  mov     rcx, cs:WPP_GLOBAL_Control
0x180007154  cmp     rcx, rsi
0x180007157  jz      short loc_180007178
0x180007159  test    byte ptr [rcx+1Ch], 20h
0x18000715d  jz      short loc_180007178
0x18000715f  mov     edx, 39h ; '9'
0x180007164  mov     r9, rax
0x180007167  lea     r8, WPP_cf54b1e076d23b7381661ccc00326d94_Traceguids
0x18000716e  mov     rcx, [rcx+10h]
0x180007172  call    WPP_SF_S
0x180007177  nop
0x180007178  jmp     short $+2
0x18000717a  mov     ebx, [rsp+158h+var_138]
0x18000717e  lea     rcx, [rsp+158h+var_128]; this
0x180007183  call    ??1CESTTrackFn@@QEAA@XZ; CESTTrackFn::~CESTTrackFn(void)
0x180007188  mov     eax, ebx
0x18000718a  mov     rcx, [rsp+158h+var_18]
0x180007192  xor     rcx, rsp; StackCookie
0x180007195  call    __security_check_cookie
0x18000719a  lea     r11, [rsp+158h+var_8]
0x1800071a2  mov     rbx, [r11+20h]
0x1800071a6  mov     rsi, [r11+28h]
0x1800071aa  mov     rsp, r11
0x1800071ad  pop     rdi
0x1800071ae  retn
```
