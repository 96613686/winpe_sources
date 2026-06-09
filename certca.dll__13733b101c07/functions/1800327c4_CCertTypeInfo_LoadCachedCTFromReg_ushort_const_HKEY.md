# CCertTypeInfo::_LoadCachedCTFromReg(ushort const *,HKEY__ *)

- ea: `0x1800327c4`
- end: `0x18003289b`
- name: `?_LoadCachedCTFromReg@CCertTypeInfo@@IEAAJPEBGPEAUHKEY__@@@Z`
- size: `215`
- prototype: `__int64 __fastcall(CCertTypeInfo *this, unsigned __int16 *Src, HKEY, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180031ddc`

## callees

- `0x18000b800`
- `0x18000ce90`
- `0x1800113e0`
- `0x1800327c4`
- `0x1800353dc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180032883`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180032883`

## pseudocode

```c
__int64 __fastcall CCertTypeInfo::_LoadCachedCTFromReg(
        CCertTypeInfo *this,
        unsigned __int16 *Src,
        HKEY a3,
        unsigned int a4)
{
  int v6; // eax
  unsigned int v7; // ebx
  unsigned __int16 *v8; // rax
  unsigned __int16 *v10; // [rsp+30h] [rbp-18h] BYREF
  __int64 v11; // [rsp+38h] [rbp-10h]
  HKEY hKey; // [rsp+68h] [rbp+20h] BYREF

  hKey = 0;
  v6 = ctRegOpenKeyEx(a3, Src, (unsigned int)a3, a4, &hKey);
  v7 = v6;
  if ( v6 )
  {
    if ( v6 > 0 )
      v7 = (unsigned __int16)v6 | 0x80070000;
  }
  else
  {
    v7 = CCertTypeInfo::_LoadFromRegBase(this, Src, hKey);
    if ( !v7 )
    {
      v8 = CertAllocString(Src);
      *((_QWORD *)this + 1) = v8;
      if ( v8 )
      {
        v10 = v8;
        v11 = 0;
        CCertTypeInfo::SetProperty(this, L"cn", &v10);
        v10 = Src;
        v11 = 0;
        CCertTypeInfo::SetProperty(this, L"distinguishedName", &v10);
        v7 = 0;
      }
      else
      {
        v7 = -2147024882;
      }
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v7;
}

```

## disassembly

```asm
0x1800327c4  mov     r11, rsp
0x1800327c7  mov     [r11+8], rbx
0x1800327cb  mov     [r11+10h], rsi
0x1800327cf  push    rdi
0x1800327d0  sub     rsp, 40h
0x1800327d4  mov     rdi, rcx
0x1800327d7  mov     qword ptr [r11+20h], 0
0x1800327df  lea     rax, [r11+20h]
0x1800327e3  mov     rcx, r8; HKEY
0x1800327e6  mov     [r11-28h], rax
0x1800327ea  mov     rsi, rdx
0x1800327ed  call    ?ctRegOpenKeyEx@@YAJPEAUHKEY__@@PEBGKKPEAPEAU1@@Z; ctRegOpenKeyEx(HKEY__ *,ushort const *,ulong,ulong,HKEY__ * *)
0x1800327f2  mov     ebx, eax
0x1800327f4  test    eax, eax
0x1800327f6  jz      short loc_180032805
0x1800327f8  jle     short loc_180032879
0x1800327fa  movzx   ebx, ax
0x1800327fd  or      ebx, 80070000h
0x180032803  jmp     short loc_180032879
0x180032805  mov     r8, [rsp+48h+hKey]; HKEY
0x18003280a  mov     rdx, rsi; unsigned __int16 *
0x18003280d  mov     rcx, rdi; this
0x180032810  call    ?_LoadFromRegBase@CCertTypeInfo@@IEAAJPEBGPEAUHKEY__@@@Z; CCertTypeInfo::_LoadFromRegBase(ushort const *,HKEY__ *)
0x180032815  mov     ebx, eax
0x180032817  test    eax, eax
0x180032819  jnz     short loc_180032879
0x18003281b  mov     rcx, rsi; Src
0x18003281e  call    ?CertAllocString@@YAPEAGPEBG@Z; CertAllocString(ushort const *)
0x180032823  mov     [rdi+8], rax
0x180032827  test    rax, rax
0x18003282a  jnz     short loc_180032833
0x18003282c  mov     ebx, 8007000Eh
0x180032831  jmp     short loc_180032879
0x180032833  lea     r8, [rsp+48h+var_18]; unsigned __int16 **
0x180032838  mov     [rsp+48h+var_18], rax
0x18003283d  lea     rdx, aCn_1; "cn"
0x180032844  mov     [rsp+48h+var_10], 0
0x18003284d  mov     rcx, rdi; this
0x180032850  call    ?SetProperty@CCertTypeInfo@@QEAAJPEBGPEAPEAG@Z; CCertTypeInfo::SetProperty(ushort const *,ushort * *)
0x180032855  lea     r8, [rsp+48h+var_18]; unsigned __int16 **
0x18003285a  mov     [rsp+48h+var_18], rsi
0x18003285f  lea     rdx, aDistinguishedn; "distinguishedName"
0x180032866  mov     [rsp+48h+var_10], 0
0x18003286f  mov     rcx, rdi; this
0x180032872  call    ?SetProperty@CCertTypeInfo@@QEAAJPEBGPEAPEAG@Z; CCertTypeInfo::SetProperty(ushort const *,ushort * *)
0x180032877  xor     ebx, ebx
0x180032879  mov     rcx, [rsp+48h+hKey]; hKey
0x18003287e  test    rcx, rcx
0x180032881  jz      short loc_180032889
0x180032883  call    cs:__imp_RegCloseKey
0x180032889  mov     rsi, [rsp+48h+arg_8]
0x18003288e  mov     eax, ebx
0x180032890  mov     rbx, [rsp+48h+arg_0]
0x180032895  add     rsp, 40h
0x180032899  pop     rdi
0x18003289a  retn
```
