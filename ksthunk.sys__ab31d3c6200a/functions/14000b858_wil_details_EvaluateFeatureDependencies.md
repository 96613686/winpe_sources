# wil_details_EvaluateFeatureDependencies

- ea: `0x14000b858`
- end: `0x14000b93c`
- name: `wil_details_EvaluateFeatureDependencies`
- size: `228`
- prototype: `void()`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14000bac0`
- `0x14000e15c`

## callees

- `0x14000b858`
- `0x14000b944`

## pseudocode

```c
void wil_details_EvaluateFeatureDependencies()
{
  __int64 **i; // r9
  volatile signed __int32 **v1; // rcx
  unsigned int v2; // r10d
  volatile signed __int32 v3; // edx
  int v4; // eax
  __int64 *v5; // r11
  __int64 v6; // r9

  i = wil_details_featureDescriptors_a;
  v1 = (volatile signed __int32 **)wil_details_featureDescriptors_a;
  if ( wil_details_featureDescriptors_a < (__int64 **)wil_details_featureDescriptors_z )
  {
    while ( !*v1 )
    {
      if ( ++v1 >= (volatile signed __int32 **)wil_details_featureDescriptors_z )
        goto LABEL_21;
    }
    if ( !v1 )
      goto LABEL_21;
    v2 = 0;
    do
    {
      v3 = **v1;
      if ( (v3 & 0x200) != 0 )
      {
        v4 = 0;
        if ( (v3 & 0x180) != 0 )
          LOBYTE(v4) = (**v1 & 0x180) == 256;
        else
          LOBYTE(v4) = *((_BYTE *)v1 + 31) != 0;
        v2 = v2 & 0xFFFFFFBF | (v4 << 6) ^ **v1 & 0x40;
        _InterlockedXor(*v1, v2);
      }
      for ( v1 += 7; ; ++v1 )
      {
        if ( v1 >= (volatile signed __int32 **)wil_details_featureDescriptors_z )
          goto LABEL_21;
        if ( *v1 )
          break;
      }
    }
    while ( v1 );
LABEL_21:
    while ( i < (__int64 **)wil_details_featureDescriptors_z )
    {
      if ( *i )
      {
LABEL_28:
        if ( i )
        {
          wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState(*i, i);
          for ( i = (__int64 **)(v6 + 56); i < (__int64 **)wil_details_featureDescriptors_z; ++i )
          {
            if ( *i != v5 )
              goto LABEL_28;
          }
        }
        return;
      }
      ++i;
    }
  }
}

```

## disassembly

```asm
0x14000b858  push    rbx
0x14000b85a  sub     rsp, 20h
0x14000b85e  xor     r11d, r11d
0x14000b861  lea     r9, wil_details_featureDescriptors_a
0x14000b868  lea     rbx, wil_details_featureDescriptors_z
0x14000b86f  mov     [rsp+28h+arg_0], r11
0x14000b874  mov     rcx, r9
0x14000b877  cmp     r9, rbx
0x14000b87a  jnb     loc_14000B935
0x14000b880  cmp     [rcx], r11
0x14000b883  jnz     short loc_14000B890
0x14000b885  add     rcx, 8
0x14000b889  cmp     rcx, rbx
0x14000b88c  jb      short loc_14000B880
0x14000b88e  jmp     short loc_14000B908
0x14000b890  test    rcx, rcx
0x14000b893  jz      short loc_14000B908
0x14000b895  mov     r10d, dword ptr [rsp+28h+arg_0]
0x14000b89a  mov     rax, [rcx]
0x14000b89d  mov     edx, [rax]
0x14000b89f  bt      edx, 9
0x14000b8a3  jnb     short loc_14000B8E2
0x14000b8a5  mov     r8d, edx
0x14000b8a8  mov     eax, r11d
0x14000b8ab  and     r8d, 180h
0x14000b8b2  jnz     short loc_14000B8BD
0x14000b8b4  cmp     [rcx+1Fh], r11b
0x14000b8b8  setnz   al
0x14000b8bb  jmp     short loc_14000B8C7
0x14000b8bd  cmp     r8d, 100h
0x14000b8c4  setz    al
0x14000b8c7  shl     eax, 6
0x14000b8ca  and     edx, 40h
0x14000b8cd  xor     edx, eax
0x14000b8cf  mov     eax, r10d
0x14000b8d2  and     eax, 0FFFFFFBFh
0x14000b8d5  mov     r10d, edx
0x14000b8d8  or      r10d, eax
0x14000b8db  mov     rax, [rcx]
0x14000b8de  lock xor [rax], r10d
0x14000b8e2  add     rcx, 38h ; '8'
0x14000b8e6  jmp     short loc_14000B8F1
0x14000b8e8  cmp     [rcx], r11
0x14000b8eb  jnz     short loc_14000B8F8
0x14000b8ed  add     rcx, 8
0x14000b8f1  cmp     rcx, rbx
0x14000b8f4  jb      short loc_14000B8E8
0x14000b8f6  jmp     short loc_14000B908
0x14000b8f8  test    rcx, rcx
0x14000b8fb  jnz     short loc_14000B89A
0x14000b8fd  jmp     short loc_14000B908
0x14000b8ff  cmp     [r9], r11
0x14000b902  jnz     short loc_14000B930
0x14000b904  add     r9, 8
0x14000b908  cmp     r9, rbx
0x14000b90b  jb      short loc_14000B8FF
0x14000b90d  jmp     short loc_14000B935
0x14000b90f  mov     rcx, [r9]
0x14000b912  mov     rdx, r9
0x14000b915  call    wil_details_EvaluateFeatureDependencies_GetCachedFeatureEnabledState
0x14000b91a  add     r9, 38h ; '8'
0x14000b91e  jmp     short loc_14000B929
0x14000b920  cmp     [r9], r11
0x14000b923  jnz     short loc_14000B930
0x14000b925  add     r9, 8
0x14000b929  cmp     r9, rbx
0x14000b92c  jb      short loc_14000B920
0x14000b92e  jmp     short loc_14000B935
0x14000b930  test    r9, r9
0x14000b933  jnz     short loc_14000B90F
0x14000b935  add     rsp, 20h
0x14000b939  pop     rbx
0x14000b93a  retn
```
