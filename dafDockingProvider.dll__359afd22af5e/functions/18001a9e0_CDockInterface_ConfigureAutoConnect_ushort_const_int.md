# CDockInterface::ConfigureAutoConnect(ushort const *,int)

- ea: `0x18001a9e0`
- end: `0x18001aac1`
- name: `?ConfigureAutoConnect@CDockInterface@@UEAAJPEBGH@Z`
- size: `225`
- prototype: `__int64 __fastcall(CDockInterface *__hidden this, const unsigned __int16 *, int)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x1800104e4`
- `0x18001471c`
- `0x18001a9e0`
- `0x18001abac`
- `0x18001ca3e`
- `0x18001ca70`

## pseudocode

```c
__int64 __fastcall CDockInterface::ConfigureAutoConnect(CDockInterface *this, const unsigned __int16 *a2, int a3)
{
  __int64 result; // rax
  __int64 v7; // rcx
  int v8; // ebx
  _BYTE v9[1144]; // [rsp+30h] [rbp-4B8h] BYREF
  unsigned __int64 v10; // [rsp+4A8h] [rbp-40h]

  memset_0(v9, 0, 0x488u);
  result = CDockInterface::DeviceInstancePathToDockProfile(this, a2, (struct _DOCK_PROFILE *)v9);
  if ( (int)result >= 0 )
  {
    v7 = *((_QWORD *)this + 2);
    if ( v10 >= *(unsigned int *)(v7 + 16) )
    {
      v8 = -2147024809;
    }
    else
    {
      v8 = DockingProvider::ConfigureAutoConnect(
             *(DockingProvider **)(*(_QWORD *)(v7 + 24) + 8 * v10),
             (struct _DOCK_PROFILE *)v9,
             a3);
      if ( v8 >= 0 )
        return 0;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25)
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_qdS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        16,
        (unsigned int)&WPP_b415491bb2933ebae3e7436051291308_Traceguids,
        (_DWORD)this,
        v8,
        (__int64)a2);
    }
    return (unsigned int)v8;
  }
  return result;
}

```

## disassembly

```asm
0x18001a9e0  push    rbx
0x18001a9e2  push    rsi
0x18001a9e3  push    rdi
0x18001a9e4  sub     rsp, 4D0h
0x18001a9eb  mov     rax, cs:__security_cookie
0x18001a9f2  xor     rax, rsp
0x18001a9f5  mov     [rsp+4E8h+var_28], rax
0x18001a9fd  mov     ebx, r8d
0x18001aa00  mov     rsi, rdx
0x18001aa03  mov     rdi, rcx
0x18001aa06  xor     edx, edx; Val
0x18001aa08  mov     r8d, 488h; Size
0x18001aa0e  lea     rcx, [rsp+4E8h+var_4B8]; void *
0x18001aa13  call    memset_0
0x18001aa18  lea     r8, [rsp+4E8h+var_4B8]; struct _DOCK_PROFILE *
0x18001aa1d  mov     rdx, rsi; unsigned __int16 *
0x18001aa20  mov     rcx, rdi; this
0x18001aa23  call    ?DeviceInstancePathToDockProfile@CDockInterface@@AEAAJPEBGPEAU_DOCK_PROFILE@@@Z; CDockInterface::DeviceInstancePathToDockProfile(ushort const *,_DOCK_PROFILE *)
0x18001aa28  test    eax, eax
0x18001aa2a  js      short loc_18001AAA6
0x18001aa2c  mov     rcx, [rdi+10h]
0x18001aa30  mov     r9, [rsp+4E8h+var_40]
0x18001aa38  mov     eax, [rcx+10h]
0x18001aa3b  cmp     r9, rax
0x18001aa3e  jnb     short loc_18001AA5F
0x18001aa40  mov     rcx, [rcx+18h]
0x18001aa44  lea     rdx, [rsp+4E8h+var_4B8]; struct _DOCK_PROFILE *
0x18001aa49  mov     r8d, ebx; int
0x18001aa4c  mov     rcx, [rcx+r9*8]; this
0x18001aa50  call    ?ConfigureAutoConnect@DockingProvider@@QEAAJPEAU_DOCK_PROFILE@@H@Z; DockingProvider::ConfigureAutoConnect(_DOCK_PROFILE *,int)
0x18001aa55  mov     ebx, eax
0x18001aa57  test    eax, eax
0x18001aa59  js      short loc_18001AA64
0x18001aa5b  xor     eax, eax
0x18001aa5d  jmp     short loc_18001AAA6
0x18001aa5f  mov     ebx, 80070057h
0x18001aa64  mov     rcx, cs:WPP_GLOBAL_Control
0x18001aa6b  lea     rax, WPP_GLOBAL_Control
0x18001aa72  cmp     rcx, rax
0x18001aa75  jz      short loc_18001AAA4
0x18001aa77  cmp     byte ptr [rcx+19h], 1
0x18001aa7b  jb      short loc_18001AAA4
0x18001aa7d  test    byte ptr [rcx+1Ch], 1
0x18001aa81  jz      short loc_18001AAA4
0x18001aa83  mov     rcx, [rcx+10h]
0x18001aa87  lea     r8, WPP_b415491bb2933ebae3e7436051291308_Traceguids
0x18001aa8e  mov     edx, 10h
0x18001aa93  mov     [rsp+4E8h+var_4C0], rsi
0x18001aa98  mov     r9, rdi
0x18001aa9b  mov     [rsp+4E8h+var_4C8], ebx
0x18001aa9f  call    WPP_SF_qdS
0x18001aaa4  mov     eax, ebx
0x18001aaa6  mov     rcx, [rsp+4E8h+var_28]
0x18001aaae  xor     rcx, rsp; StackCookie
0x18001aab1  call    __security_check_cookie
0x18001aab6  add     rsp, 4D0h
0x18001aabd  pop     rdi
0x18001aabe  pop     rsi
0x18001aabf  pop     rbx
0x18001aac0  retn
```
