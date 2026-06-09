# CUniscribe::ItemizeString(tagUSP_CLIENT *,ushort,int *,ushort *,int,int,ushort,int)

- ea: `0x180032c44`
- end: `0x180032d55`
- name: `?ItemizeString@CUniscribe@@QEAAHPEAUtagUSP_CLIENT@@GPEAHPEAGHHGH@Z`
- size: `273`
- prototype: `__int64 __fastcall(CUniscribe *__hidden this, struct tagUSP_CLIENT *, unsigned __int16, int *, WCHAR *pwcInChars, int cInChars, int, unsigned __int16, int)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180031ffc`
- `0x18008d6a0`

## callees

- `0x180032c44`

## import_xrefs

- `KERNEL32!GetThreadLocale` at `0x180032c99`
- `KERNEL32!GetThreadLocale` at `0x180032c99`
- `USP10!ScriptItemize` at `0x180032d20`
- `USP10!ScriptItemize` at `0x180032d20`

## pseudocode

```c
__int64 __fastcall CUniscribe::ItemizeString(
        CUniscribe *this,
        struct tagUSP_CLIENT *a2,
        __int16 a3,
        int *a4,
        WCHAR *pwcInChars,
        int cInChars,
        int a7,
        unsigned __int16 a8,
        int a9)
{
  __int64 v9; // rax
  __int16 v10; // dx
  SCRIPT_ITEM *pItems; // r15
  unsigned __int16 v14; // ax
  SCRIPT_CONTROL *p_psControl; // rbx
  const SCRIPT_STATE *psState; // rdi
  __int16 ThreadLocale; // ax
  __int64 result; // rax
  int pcItems[4]; // [rsp+40h] [rbp-10h] BYREF
  CUniscribe *v20; // [rsp+80h] [rbp+30h] BYREF
  SCRIPT_CONTROL psControl; // [rsp+88h] [rbp+38h] BYREF

  v20 = this;
  v9 = *(_QWORD *)a2;
  v10 = 0;
  pItems = *(SCRIPT_ITEM **)(v9 + 16);
  psControl = 0;
  LOWORD(v20) = 0;
  pcItems[0] = 0;
  if ( a7 )
  {
    v14 = a8;
    p_psControl = &psControl;
    psState = (const SCRIPT_STATE *)&v20;
    if ( !a8 )
    {
      ThreadLocale = GetThreadLocale();
      v10 = (__int16)v20;
      v14 = ThreadLocale & 0x3FF;
    }
    *(_WORD *)&psControl = v14;
    psControl = (SCRIPT_CONTROL)((*(_DWORD *)&psControl ^ (a9 << 23)) & 0x800000 ^ *(_DWORD *)&psControl);
    if ( psControl == 1 )
      v10 ^= (v10 ^ (a3 << 11)) & 0x800;
    LOWORD(v20) = v10 ^ ((unsigned __int8)a3 ^ (unsigned __int8)v10) & 0x1F;
  }
  else
  {
    p_psControl = 0;
    psState = 0;
  }
  if ( ScriptItemize(pwcInChars, cInChars, cInChars + 1, p_psControl, psState, pItems, pcItems) < 0 )
    return 0;
  result = (unsigned int)pcItems[0];
  *a4 = pcItems[0];
  return result;
}

```

## disassembly

```asm
0x180032c44  mov     [rsp-28h+arg_10], rbx
0x180032c49  mov     [rsp-28h+arg_18], rsi
0x180032c4e  mov     [rsp-28h+arg_0], rcx
0x180032c53  push    rbp
0x180032c54  push    rdi
0x180032c55  push    r12
0x180032c57  push    r14
0x180032c59  push    r15
0x180032c5b  mov     rbp, rsp
0x180032c5e  sub     rsp, 50h
0x180032c62  mov     rax, [rdx]
0x180032c65  xor     r12d, r12d
0x180032c68  mov     edx, r12d
0x180032c6b  mov     r14, r9
0x180032c6e  movzx   esi, r8w
0x180032c72  mov     r15, [rax+10h]
0x180032c76  mov     dword ptr [rbp+psControl.uDefaultLanguage], r12d
0x180032c7a  mov     word ptr [rbp+arg_0], dx
0x180032c7e  mov     [rbp+var_10], r12d
0x180032c82  cmp     [rbp+arg_30], r12d
0x180032c86  jz      short loc_180032CF9
0x180032c88  movzx   eax, [rbp+arg_38]
0x180032c8c  lea     rbx, [rbp+psControl]
0x180032c90  lea     rdi, [rbp+arg_0]
0x180032c94  test    ax, ax
0x180032c97  jnz     short loc_180032CB1
0x180032c99  call    cs:__imp_GetThreadLocale
0x180032ca0  nop     dword ptr [rax+rax+00h]
0x180032ca5  movzx   edx, word ptr [rbp+arg_0]
0x180032ca9  mov     ecx, 3FFh
0x180032cae  and     ax, cx
0x180032cb1  mov     ecx, [rbp+arg_40]
0x180032cb4  shl     ecx, 17h
0x180032cb7  mov     word ptr [rbp+psControl.uDefaultLanguage], ax
0x180032cbb  mov     eax, dword ptr [rbp+psControl.uDefaultLanguage]
0x180032cbe  xor     ecx, eax
0x180032cc0  and     ecx, 800000h
0x180032cc6  xor     eax, ecx
0x180032cc8  mov     dword ptr [rbp+psControl.uDefaultLanguage], eax
0x180032ccb  cmp     ax, 1
0x180032ccf  jnz     short loc_180032CE6
0x180032cd1  movzx   eax, si
0x180032cd4  mov     ecx, 800h
0x180032cd9  shl     ax, 0Bh
0x180032cdd  xor     ax, dx
0x180032ce0  and     ax, cx
0x180032ce3  xor     dx, ax
0x180032ce6  movzx   eax, dx
0x180032ce9  xor     ax, si
0x180032cec  and     ax, 1Fh
0x180032cf0  xor     ax, dx
0x180032cf3  mov     word ptr [rbp+arg_0], ax
0x180032cf7  jmp     short loc_180032CFF
0x180032cf9  mov     rbx, r12
0x180032cfc  mov     rdi, r12
0x180032cff  mov     edx, [rbp+cInChars]; cInChars
0x180032d02  lea     rax, [rbp+var_10]
0x180032d06  mov     rcx, [rbp+pwcInChars]; pwcInChars
0x180032d0a  mov     r9, rbx; psControl
0x180032d0d  mov     [rsp+50h+pcItems], rax; pcItems
0x180032d12  mov     [rsp+50h+pItems], r15; pItems
0x180032d17  lea     r8d, [rdx+1]; cMaxItems
0x180032d1b  mov     [rsp+50h+psState], rdi; psState
0x180032d20  call    cs:__imp_ScriptItemize
0x180032d27  nop     dword ptr [rax+rax+00h]
0x180032d2c  test    eax, eax
0x180032d2e  js      short loc_180032D38
0x180032d30  mov     eax, [rbp+var_10]
0x180032d33  mov     [r14], eax
0x180032d36  jmp     short loc_180032D3B
0x180032d38  mov     eax, r12d
0x180032d3b  lea     r11, [rsp+50h+var_s0]
0x180032d40  mov     rbx, [r11+40h]
0x180032d44  mov     rsi, [r11+48h]
0x180032d48  mov     rsp, r11
0x180032d4b  pop     r15
0x180032d4d  pop     r14
0x180032d4f  pop     r12
0x180032d51  pop     rdi
0x180032d52  pop     rbp
0x180032d53  retn
```
