# CompileShader_0

- ea: `0x1801d1ba8`
- end: `0x1801d1c1c`
- name: `CompileShader_0`
- size: `116`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1801d1868`

## callees

- `0x1800389c0`
- `0x1801d1ba8`
- `0x1802d1100`
- `0x180307010`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1801d1c04`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1801d1c04`

## string_xrefs

- `0x1801d1bc4`: `cbuffer cbVSLowFreqUpdate : register(b0)\n{\n   float4 g_baseTransform;\n};\n\ncbuffer cbSolidRenderData : register(b1)\n{\n   float4 g_color;\n};\n\nfloat4\nApplyBaseTransform(float2 pt)\n{\n    return\n        float4(\n            pt.x * g_baseTransform.x + g_baseTransform.y,\n            pt.y * g_baseTransform.z + g_baseTransform.w,\n            0.5f,\n            1.0f\n            );\n}\n\nstruct VSInput\n{\n    float2 position : POSITION;\n    int2 VSInt16Data_0 : TEXCOORD0;\n};\n\nstruct P`

## pseudocode

```c

```
